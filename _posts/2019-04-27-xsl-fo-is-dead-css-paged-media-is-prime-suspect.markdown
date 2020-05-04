---
layout: post
title: XSL-FO Is Dead, CSS Paged Media Is Prime Suspect
description: There have been a number of reports that XSL-FO is a dead language and that CSS Paged Media is ready to usurp it from it's role as the industry standard for printed output. This post looks at the current state of affairs for both XSL-FO and CSS Page Media to see which is the best for building a new publishing solution.
categories: [eBooks]
tags: [CSS Paged Media, EPUB, XSL-FO]
---
> Reports of my death have been greatly exaggerated

*XSL-FO - 2014, 2015, 2016, 2017, 2018, 2019*

There have been a number of reports that XSL-FO is a dead language and that CSS Paged Media is ready to usurp it from it's role as the industry standard for printed output. 

As both a web and print developer this topic is of great interest to me, and as much as I have liked working with XSL-FO in the past I would love to be able to double down on a single language for both websites and printed media. So for this article I'm planning to see what the current state of affairs for both XSL-FO and CSS Page Media to see which is the best for building a new publishing solution.

## Update April 2019
[New article on the current state of the XSL-FO eco-system](https://www.rockweb.co.uk/blog/2019/04/xsl-fo-is-alive-and-kicking/)

## Why XSL-FO

The biggest advantage is that you can use it today without having to pay for it, there is an open source implementation of the spec in the form of the [Apache Formatting Objects Processor](http://xmlgraphics.apache.org/fop/) which is very good. I've used it for a number of commercial projects and it's more than up to the job. It's primary output format is PDF but it also supports PostScript, PCL, AFP, AWT, PNG, RFT & TXT. It also enables you to embed SVG and regular images and fonts, allowing you to create pretty much any document you can imagine.

There's also some commercial vendors such as [RenderX](http://www.renderx.com/) and [Antenna House](http://antennahouse.com/) which are more targeted towards the advanced requirements of commercial publishers. Both offer Java and .Net implementations of their processors, whilst Apache is only available in Java.

### Background

XSL-FO is part of the XSL specification from the W3C, its companion language XSLT is used for XML transformation and XSL-FO is used for formatting, specifically for paged media (print). When it was first released it was intended that XSL-FO would for print what CSS is for screens. For this task it is more than up to the job.

### Use Case

XSL-FO is a good fit for an XML based publishing work-flow, when combined with XSLT it creates a powerful way of generating documents from an XML source. I've used it to create transactional documents such as Invoices, Schedules & Letters and have used it for entire book series. It's very powerful and gives excellent results.

> My customers are getting real-world problems solved with XSL-FO 1.1.

*[G. Ken Holman.](https://plus.google.com/+GKenHolman-Crane/)*

### Learning XSL-FO

It is often said that XSL-FO is hard to learn, that it should be left to an elite FO coder that does nothing else, that mere mortal developers will turn to stone just by gazing upon the complexity of the code. This of course not true, XSL-FO is actually relatively simple once you get going. Here's an example block element with some styles applied:

	<fo:block font-family="Arial" font-size="14pt" color="red">a simple FO block</fo:block>

The same thing in HTML:

	<div style="font-family: Arial; font-size: 14pt; color:red;">a simple HTML div</div>

When we combine XSL-FO with XSLT we can even have something akin to CSS classes, called xsl-attribute-sets

	<fo:block xsl:use-attribute-sets="block-style">a simple FO block</fo:block>

	...

	<xsl:attribute-set name="block-style">
		<xsl:attribute name="font-family">Arial</xsl:attribute>
		<xsl:attribute name="font-size">14pt</xsl:attribute>
		<xsl:attribute name="color">red</xsl:attribute>
	</xsl:attribute-set>

HTML & CSS Equivalent

	<div class="block-style">a simple HTML div</div>

	...

	.block-style {
		font-family: Arial;
		font-size: 14pt;
		color: red;
	}

As a developer I've found it easy to switch between CSS and XSL-FO and in many cases especially before the introduction of CSS pre-processors like LESS or SASS I've missed the added capabilities of xsl-attribute-sets which allow you to extend existing sets (classes) leading to more modular code.

### Books

My examples are a bit basic, if you want to learn more about XSL-FO there are a couple of good books available which are still as relevant to today as they where 10 years ago, don't let the age put you off (Not something you'd hear me say about any other technology book).

#### Definitive XSL-FO by G. Ken Holman

Of the 2 books, this is the easiest to follow, and I have found myself using it more often for it's bullet listed style which makes it a great reference book. Here's the 
[Amazon link](http://www.amazon.co.uk/Definitive-XSL-FO-XML-Ken-Holman/dp/0131403745/ref=sr_1_1?ie=UTF8&qid=1401878746&sr=8-1&keywords=g+ken+holman) in case you want to get it. It was £26.57 at the time I wrote this article.


#### XSL-FO: Making XML Look Good in Print by Dave Pawson

This was the first book I ever read on XSL-FO, and whilst it can take a while to get into it's very good. It shows the stylesheets used to actually create the book using XSL-FO which gives you an idea of the power of the language. It's also full of best practices and if you can stick with it you'll end up writing better code, I certainly did. Here's the [Amazon link](http://www.amazon.co.uk/XSL-FO-Making-Look-Good-Print/dp/0596003552/ref=sr_1_1?ie=UTF8&qid=1401878789&sr=8-1&keywords=dave+pawson+xml), it was £23.01 at time of writing.

### Web Tutorial links

Some links for reference:

* [http://www.renderx.com/tutorial.html](http://www.renderx.com/tutorial.html)


### XSL-FO Rendering Engines

#### Apache FOP

Free open source implementation of XSL-FO 1.1.

| | Dollars | Pounds | Euros |
|-|-|-|-|
Server License | $0 | £0 | €0
Developer License | $0 | £0 | €0

* Interfaces: Java, Command-line
* Output Formats: PDF, PostScript, PCL, AFP, AWT, PNG, RFT, TXT
* [http://xmlgraphics.apache.org/fop/](http://xmlgraphics.apache.org/fop/)

#### RenderX XEP

Commercial implementation of XSL-FO 1.1, also available as a cloud service.

| | Dollars | Pounds | Euros |
|-|-|-|-|
Server License |$4750 | £2838 | €3489
Developer License |$400 | £239 | €239

* Interfaces: Java, .Net, Command-line
* Output Formats: PDF, PostScript, SVG, AFP, XPS, PPML, HTML
* [http://www.renderx.com/](http://www.renderx.com/)

#### Antenna House

Commercial implementation of XSL-FO 1.1 with CSS 3 support, the most fully featured and expensive option for XML printing.

| | Dollars | Pounds | Euros |
|-|-|-|-|
Server License | $7000 | £4183 | €5142 |
Developer License | $1750 | £1750 | €1285 |

* Interfaces: Java, .Net, Command-line, C/C++, COM
* Output Formats: PDF, PostScript, SVG, MIF, XPS
* [http://www.antennahouse.com](http://www.antennahouse.com)

## The case against XSL-FO

The case for XSL-FO is pretty strong, you can use it for free or pay for a commercial solution, it's stable and is an industry standard. What's not to like?

### XSL-FO Working Group has disbanded

> We have closed the Working Group because not enough people were taking part. 

*[Liam R. E. Quin](http://www.w3.org/People/Quin/)* (W3C XML Activity Lead) - November 2013 

One of the arguments for not using XSL-FO for a new project is that the W3C Working Group that looked after the specification is no longer active and is no longer maintained. It could however be spun the other way to say that it's now good enough and doesn't need further revision or extension:

> in a few short specs it was nailed pretty well and it does what 90% of the people want right now for *print*. There is really little to add to it to cover the full intention of what it should be -- a standard for the representation of Formatted (print) output.
> ...
> XSL FO will survive for a long time for those that require true print output and for a long time it will be the only Industry Standard way of doing it.

*Kevin Brown, RenderX*

### Experienced Developers (Or Lack Of)

Perhaps the ultimate nail in the coffin for XSL-FO is the lack of experienced developers. There are many more experienced web developers out there than XSL-FO developers. It will be easier (and cheaper) to hire a web developer and teach them CSS paged media, building on what they already know, than to find an experienced XSL-FO developer. Although they are out there I've trained at least 6 developers in the art.

I think another issue maybe for non Java developers there isn't many free options to get started with XSL-FO. In the .Net world for example there are some ports of Apache but they are based on the 0.20.5 edition released in 2003 and are missing a lot of the later releases features.

### Single Source Publishing Model - EPUB spanner

With the advent of eReaders, eInk devices and Tablets has come the EPUB format, which is based on HTML, CSS and JavaScript. Given the ever growing popularity of EPUB it makes sense to prioritise it's place in our work-flow, which throws a bit of a spanner into the works for XSL-FO. Current XSL-FO processors don't support EPUB, and to be honest shouldn't as it has very different use cases to fixed layout print. 

In this new world we will now need two work-flows one for EPUB and one for PDF etc, or do we? We could conceivably use an XHTML document for a source file as XHTML is a subset of XML. Then using XSLT we could add the EPUB classes for one work stream and transform to XSL-FO for the others, the only real problem with this is that in many cases XHTML is to loose a specification for building a publishing platform on. 

#### O'Reilly

Now we come to O'Reilly a publisher of technical books whose publishing platform originally used XSL-FO, but has now moved to XHTML & CSS.

##### O'Reilly's work-flow

O'Reilly replaced XSL-FO with CSS Paged Media and introduced an extra step into their work-flow in the form of [AsciiDoc](http://asciidoctor.org/docs/asciidoc-writers-guide/) (looks like [markdown](http://www.rockweb.co.uk/blog/2014/05/markdown-write-more/), AsciiDoc is a shorthand replacement for DocBook (XML Book Format))

* asciidoc > xml > html > books formats; PDF, Web, EPUB => mobi (mobi comes from EPUB)

Dynamic Elements such as; TOC, Index, Cross References are easier to do in XML/XSL than HTML which is why they haven't gone straight from AsciiDoc to HTML. The new work-flow allows authors to write docs in asciidoc on their Atlas web application (in-house application for creating the documents) or via a text editor.

They are using Antenna House for the HTML & CSS to PDF conversion allowing them to migrate existing titles without loosing functionality thanks to Antenna Houses CSS extended properties.

##### HTMLBook

In the future they plan to move to their own HTML based spec called [HTMLBook](http://oreillymedia.github.io/HTMLBook/) - O'Reilly's own spec for books (like DocBook) HTMLBook = HTML & CSS no new stuff, just more structured. 

This would allow the creation of a WYSIWYG editor that creates valid markup just for the use with HTMLBook, allowing them to remove the first two steps from their work-flow

* Htmlbook > books formats; PDF, Web, EPUB => mobi (mobi comes from EPUB)

If you want to know more about O'Reilly's solution check out this video titled [Single Source Publishing and HTML](http://chimera.labs.oreilly.com/books/1234000001694/ch01.html) by [Nellie McKesson](http://alistapart.com/author/nmckesson).

## Is CSS The Future?

Yes, I believe that within the next few years CSS will supplant XSL-FO in the world's publishing houses as it has at O'Reilly.

But as of today you can't use CSS Paged Media in a browser, according to [Mozilla](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) only basic support is currently available.

You will therefore need to use a PDF processor to transform your XHTML and CSS into a PDF.

### XHTML2PDF

Free XHTML & CSS processor

| | Dollars | Pounds | Euros |
|-|-|-|-|
Server License |$0 | £0 | €0
Developer License |$0 | £0 | €0

* Output Formats: PDF
* [https://github.com/chrisglass/xhtml2pdf](https://github.com/chrisglass/xhtml2pdf)

### Antenna House

As well as XSL-FO it also takes CSS3 and provides a couple of hundred [CSS extended properties](http://www.antennahouse.com/CSSInfo/css_reference.html#css-exproperty-conf) to fill the gap between CSS and XSL-FO.
See previous section for full details.

### Prince

PDF Processor for HTML5 & CSS it also has a number of extensions to fill the gaps in the CSS Paged Media spec.

| | Dollars | Pounds | Euros |
|-|-|-|-|
Server License: | $3800 | £2271 | €2791
Developer License: | $495 | £296 | €363

* Interfaces: Java, .Net, PHP, Ruby on Rails, COM
* Output Formats: PDF
* [http://www.princexml.com/](http://www.princexml.com/)

### Vendor lock in?

The CSS to PDF processors aren't cheap and with the number of vendor specific extended properties I'd have some concern about code portability and vendor lock-in, the current situation reminds of when we moved from Internet Explorer 6 to other browsers. 

## Conclusion

XSL-FO isn't dead yet and is still more than up to the task of being the basis of an XML based publishing system today. If you are only interested in printed media and have no plans to support EPUB I would recommend using XSL-FO without reservation.

If however you need to also support EPUB, CSS should figure in your plans, its evolving fast and the paged media spec is now a working draft which should mean browser vendors start implementing it. 

All in all it's an interesting time to be involved in print development.

## Looking for an XSL-FO or CSS Paged Media Consultant?
If you have a project that you need some expert help on, I'm available to provide consultancy and development services. Drop me an email on [hello@rockweb.co.uk](mailto:hello@rockweb.co.uk) or tweet [@rockwebuk](https://twitter.com/rockwebuk)