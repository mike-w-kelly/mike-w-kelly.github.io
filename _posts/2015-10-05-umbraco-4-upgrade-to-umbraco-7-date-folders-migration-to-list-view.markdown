---
layout: post
title: Umbraco 4 upgrade to Umbraco 7, Date Folders migration to List View
description: Date Folders migration to List View as part of the upgrade to Umbraco 7.
categories: [Umbraco]
tags: [Umbraco 7, Date Folders]
---
Doing an upgrade for a client from 4.9 to 7.2.8, I was stuck with what to do about the date folders package which isn't supported in Umbraco 7.

A quick internet search brought up an [article](https://cultiv.nl/blog/moving-from-datefolders-to-umbracos-new-listview/) by Sebastiaan Janssen a developer at Umbraco HQ. 

This got me most of the way, in summary it recommended the following steps:

Steps
- Create an API controller that calls the Content API to move the old articles to the new structure
- Create rewrite rule using regex and add to web.config

API Controller
--------------

For completeness here is the api controller code I used based on Seb's, I placed it in the Controllers folder of my web application.
    
    using System.Linq;
    using Umbraco.Core.Models;
    using Umbraco.Web.WebApi;

    namespace example.umbraco.Controllers
    {
        public class NewsController : UmbracoApiController
        {
            public void PostMoveNews()
            {
                const int newsNodeId = 1207;

                var contentService = Services.ContentService;
                var newsNode = contentService.GetById(newsNodeId);

                foreach (var article in newsNode.Descendants().OrderBy(p => p.CreateDate))
                {
                    if (article.ContentType.Alias == "NewsArticle")
                    {
                        contentService.Move(article, newsNodeId);
                    }
                }
            }
        }
    }

To run the code I fired up [Fiddler](http://www.telerik.com/fiddler) created a new post in the composer and pointed it at http://localhost/umbraco/api/news/postmovenews/ and hit execute. Around 5 minutes later my content finished migrating leaving me with some empty date folders to delete.

![][1]

Once the migration is run I'd recommend deleting this controller.

Enabling List View
------------------

Once you've moved your content to the root of your blog or news section you'll need to enable the List View. So login to the Umbraco back office and go to document type for the section.

With the document type selected click on the Structure tab and tick the "Enable list view" box. You can also customise what fields will be shown by clicking "edit".

![][2]

Now when you go to the content section you'll get the new List View which is a nice improvement over the old Date Folders, all that's left is to redirect the old urls to the new structure.


Rewrite Rule using Regex
-------------------------

My first point of call for the redirect was an IIS redirect rule as per the orginal article.

The regex was a simple modification of Seb's, the site I was migrating had urls in the structure **www.example.com/news/2015/09/article-name** which I wanted to redirect to **www.example.com/news/article-name**, Seb's regex handled a URL with the date as well as the month so I simply got rid of the second "d{1,2}\/"

Original
    (blog/\d{4}/\d{1,2}/\d{1,2}\/)(.*)

Modified
    ^(news/\d{4}/\d{1,2}\/)(.*)$

    <system.webServer>
        <rewrite>
        <rules>
            <rule name="News" stopProcessing="true">
                <match url="^(news/\d{4}/\d{1,2}\/)(.*)$" />
                <action type="Redirect" url="/news/{R:2}" />
            </rule>
        </rules>
        </rewrite>
    </system.webServer>

So I added the rule and fired up IIS Express but no joy, Umbraco appeared to be intercepting the redirect. 

URL Tracker 3.9
---------------

As I'd been planning to add the URL Tracker package anyway I figured I'd see if it was any easier to do the redirect.

So I downloaded the latest version from [our.umbraco.org](https://our.umbraco.org/projects/developer-tools/301-url-tracker) installed it and created a new rule.

![][3]

It differs slightly from the IIS rule in that the Redirect URL parameter uses $2 rather than R:2 to select the result of the 2nd reg ex expression. Once I got my head around this it was simple and the end result is the redirect now works as expected.

Issue with IIS Rewrite
----------------------

After I'd gotten the URL Tracker example working I went back and took a closer look at the IIS Rewrite not working, turns out I'd put the rewrite rule in the wrong place. 

I'd originally added it to:

    <location path="umbraco">
        <system.webServer>      
            <!-- rewrite code -->
        </system.webServer>
    </location>

Rather than the first instance of the <system.webServer> in the web.config. Once I moved it to the correct place the rule worked as expected in IIS Express.

Still it's good to know we have other options to IIS Rewrite for redirecting URL's in Umbraco.

  [1]: /assets/img/fiddler-api-call.PNG
  [2]: /assets/img/umbraco-enable-list-view.PNG
  [3]: /assets/img/umbraco-url-tracker-redirect-rule.PNG
