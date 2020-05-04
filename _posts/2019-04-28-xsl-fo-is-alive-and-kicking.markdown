---
layout: post
title: XSL-FO is alive and kicking
description: When I last looked at XSL-FO in 2014, it looked dead, yet 5 years later in 2019 XSL-FO is still here with commercial and open source vendors still supporting it, with updates to their products.
categories: [eBooks]
tags: [XSL-FO, Apache-FOP]
---
When I last looked at [XSL-FO](https://www.rockweb.co.uk/blog/2014/06/xsl-fo-is-dead,-css-paged-media-is-prime-suspect/) in 2014 it really looked like the writing was on the wall, that CSS Paged Media was going to be the end of XSL-FO by offering a much better product. Yet now in 2019 it's still here and surprisingly CSS Paged Media hasn't really taken off. I put this down to lack of full support in the major browsers, and tools like [Prince XML](https://www.princexml.com/), which like the commercial XSL-FO renderers before it, are expensive and niche ($3800 USD per server at time of writing). That and XSL-FO is a mature and established language and toolset that does a job well.

For the guys that can't afford these prices, they often make do with the likes of [WKhtmlToPDF](https://wkhtmltopdf.org/) or the many wrappers for it like [Rotativa](https://github.com/webgio/Rotativa) in .Net or [Java WKhtmlToPDF Wrapper](https://github.com/jhonnymertz/java-wkhtmltopdf-wrapper). But could XSL-FO be a better option?

Use cases for XSL-FO
--------------------
When should we be using XSL-FO over other tools? This is a good question to ask yourself, if you are doing a simple 1 page document with some variables, then XSL-FO is probably a sledge hammer to crack a nut. But anything more complex than that and it's still the best solution in my book for data driven transaction documents. I've used it for some of the following:
- Insurance Policy Documents
- Insurance Certificates
- Letters
- Customer Statements
- Customer Bills

Hows the XSL-FO eco-system doing?
------------------------------------
So assuming your still with me and thinking of giving XSL-FO a go for your next documents project, how is the eco-system doing? Well it's alive and kicking, the main vendors are still updating and supporting their XSL-FO rendering engines. With the three main players all having an update in the last 12 months. In fact Antenna House updated their formatter only 2 days ago.

### RenderX XEP
Last updated in October 2018 with the release of [XEP 4.28](http://www.renderx.com/news/index.html#October_11,_2018) prices currently start at $4750 USD.

### Apache FOP
Last updated in May 2018 with the release of [Apache FOP 2.3](https://xmlgraphics.apache.org/fop/download.html) and is still free.

### Antenna House Formatter
Last updated in April 2019 with the release of [Formatter V6.6 MR5](https://www.antennahouse.com/2019/04/formatter-v6-6-mr5/) prices currently starts at $5000 USD.

## Which should I use?
I'd recommend Apache FOP as the starting point, and if you need more advanced features take a look at the commercial vendors. I think you'll be surprised at what it can do.

## Learning Resources
So how do I go about getting starting with XSL-FO today. Well not so long ago I'd have directed you to w3schools, but they've taken the XSL-FO content down and the old Dave Pawson site also seems to have gone. RenderX still have some good content on their site, see the [RenderX XSL-FO Tutorial](http://www.renderx.com/tutorial.html), and there is still the books on Amazon:
- [XSL-FO: Making XML Look Good in Print by Dave Pawson](https://www.amazon.co.uk/XSL-FO-Making-Look-Good-Print/dp/0596003552/ref=sr_1_1?ie=UTF8&qid=1401878789&sr=8-1&keywords=dave+pawson+xml)
- [Definitive XSL-FO by G. Ken Holman](https://www.amazon.co.uk/Definitive-XSL-FO-XML-Ken-Holman/dp/0131403745/ref=sr_1_2?keywords=xsl-fo&qid=1556379818&s=gateway&sr=8-2)

Of the two books, "Definitive XSL-FO" is the easiest to follow. I'll be adding some getting started blog posts to show XSL-FO in the modern era in the coming months, so watch this space.

## Conclusion
XSL-FO still looks to be the best fit for complex data driven documents, give it a try today.

## Looking for some help with an XSL-FO project?
If you have a project that you need some expert help on, I'm available to provide consultancy and development services. Drop me an email on [hello@rockweb.co.uk](mailto:hello@rockweb.co.uk) or tweet [@rockwebuk](https://twitter.com/rockwebuk)
