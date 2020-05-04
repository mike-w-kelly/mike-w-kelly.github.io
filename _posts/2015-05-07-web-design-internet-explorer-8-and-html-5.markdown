---
layout: post
title: Web Design - Internet Explorer 8 and HTML 5
description: How to use HTML 5 and CSS 3 with Internet Explorer 8.
categories: [Design]
tags: [CSS 3, HTML 5, IE8]
---
Internet Explorer 8 still accounts for [3.78% of all web traffic](http://www.w3counter.com/globalstats.php) marginally behind Internet Explorer 11 which stands at 5.36%. Given this most web designers and developers will have to continue supporting IE8. 

Many of us had assumed with the demise of official support for Windows XP (for which Internet Explorer 8 was the latest version of IE available) web designers would be able to totally drop support. This unfortunately doesn't appear to be the case, a client of mine is still earning £500k a year in revenue from customers on IE8, so ignore it at your peril.

## Impact
IE8 doesn't natively support HTML 5 or CSS 3, which poses some questions about how web designers continue to support it whilst moving to these technologies. 

### Conditional Comments and Browser Specific Stylesheets
One approach could be to use conditional comments to target IE8 specifically, this is an approach many web designers have taken to target Internet Explorer bugs for earlier versions, but it works just as well for alternative styles: 

	<!--[if IE 8]>
	<link rel="stylesheet" type="text/css" media="screen"  href="ie8.css" />
	<![endif]-->

#### Pros
* You can target IE8 users specifically and ensure their experience is a good one
* You can still use CSS 3, but IE8 won't display it

#### Cons
* You have to maintain 2 lots of stylesheet markup, which will drive costs up
* You may need additional HTML markup and media to support IE8 for rounded corners etc
* Your size of your page will be bigger for older browsers

### Browser Upgrade
Another approach could be to tell users that their browser is unsupported and ask them to upgrade:

	<!--[if IE 8]>
	<h1>Please upgrade your browser!</h1>
	<![endif]-->

#### Pros
* You don't have to support IE8

#### Cons
* You could lose sales (remember the client with £500k still coming via IE8)
* It looks unprofessional and will likely drive users to vent their frustration on online forums or twitter, Google "unsupported browser detected" to see what I mean

I'd recommend not following this approach, but having seen it so often I felt it needed mentioning.

### Progressive Enhancement
An approach I'd strongly recommend with IE8 is progressive enhancement. We ensure that IE8 works well and is fully functional before layering additional styles on top for browsers that support them. To ensure you're not limiting yourself to XHTML I'd recommend using the HTML 5 doctype <!DOCTYPE html> and using [HTML 5 shiv](https://github.com/aFarkas/html5shiv) to use JavaScript to inject the new HTML 5 elements in to your page enabling you to style them even in IE8.

#### Pros
* One approach
* Semantic HTML with no extra elements just for styling

#### Cons
* IE8 style / presentation isn't as good as it could be using older techniques

## Polyfills
What if web designers could use HTML 5 & CSS 3 with IE8? Well you can to a certain extent, there are now some polyfills (JavaScript implementations of new browser features for older browsers) that enable the use of new features with minimal effort.

### [CSS3PIE](http://css3pie.com/)
Short for Progressive Internet Explorer, CSS3PIE brings some of the more useful and popular features of CSS3 to older versions of Internet Explorer 6, 7 & 8. 

* border-radius
* box-shadow
* border-image
* backgrounds
* gradients
* rgba colour values

It uses a combination of JavaScript and IE specific filters (from the time before Microsoft got standards) to achieve similar effects to CSS3. It needs a web server to run so if you try it on your file system with no results you'll know why. 

### [Selectivizr](http://selectivizr.com/) 
If you want to use the new CSS 3 selectors such as :first-child selectivizr is for you, its dependent on having a JavaScript library such as jQuery or MooTools on your site (who doesn't these days). Not all libraries are equal though see the [selectivizr](http://selectivizr.com/) home page to see what's supported for your library of choice.

### [Respond.js](https://github.com/scottjehl/Respond/)
Respond is a lightweight JavaScript polyfill for min / max width CSS media queries, if your doing responsive design and want to let IE8 share in the fun you'll need to add this to your site. Otherwise if you've taken a mobile first approach IE8 will render the mobile version of your site which is likely to look a little odd on a desktop monitor.

### [HTML5Shiv](https://github.com/aFarkas/html5shiv)
As mentioned earlier in the article HTML 5 Shiv injects HTML 5 elements into the DOM (Document Object Model) allowing web designers to style the new elements in older versions of Internet Explorer. Without it IE8 won't apply your styles and you'll end up with a broken page.

## Conclusion
There are a number of techniques and tools available to let web designers use HTML 5 and CSS 3 with older browsers enabling our customers experience our sites the way we intended whilst reducing the cost of development. If you've been holding off using HTML 5 because of IE8, nows the time to make the move.

## Don't worry you won't have to support Internet Explorer 8 forever
Microsoft have announced they're [no longer supporting old versions of Internet Explorer]( http://blogs.msdn.com/b/ie/archive/2014/08/07/stay-up-to-date-with-internet-explorer.aspx) as of January 12, 2016.
