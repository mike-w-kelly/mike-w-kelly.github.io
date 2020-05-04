---
layout: post
title: Apache FOP 2.0 released, now with rounded corners, Apple to investigate
description: Apache FOP (Formating Objects Processor) 2.0 used for transforming XSL-FO (eXtensible Stylesheet Language) to PDF among other formats was released on 3rd June 2015. New features include; rounded corners, side floats and OpenType CFF font support.
categories: [eBooks]
tags: [XSL-FO, Apache FOP]
---
Apache FOP (Formating Objects Processor) 2.0 used for transforming XSL-FO (e**X**tensible **S**tylesheet **L**anguage) to PDF among other formats was released on 3rd June 2015.

## What's new in Apache FOP 2.0

- Side float support
- Support for rounded corners
- Support for OpenType CFF fonts
- SVG graphics can use FOP custom fonts
- Extension to resize background images

See the [release notes](https://xmlgraphics.apache.org/fop/2.0/releaseNotes_2.0.html) for all the new features.

## Rounded Corners
The new feature I'm most interested in is Rounded Corners, after working with modern web browsers were this is trivial, it has always been a bit frustrating reverting to SVG or images to get the same effect in XSL-FO.

To try it out I ran the example file rounded-corners.fo which comes in the FOP 2.0 download (examples/fo/advanced/rounded-corners.fo). The FOP developers have done a good job of making it work just like the HTML & CSS equivalent. Here are two examples one rendered with Apache FOP 2.0 and the other with Google Chrome.

### XSL-FO rounded corners example

#### Code

	<fo:block 
		border-style="solid" 
		border-width="10" 
		border-color="#00f" 
		fox:border-radius="20pt" 
		padding="20pt" 
		text-align="center" 
		margin-bottom="10pt">
		Circular corners are specified when 'border-radius' is set to a single value.  This value is the radius of the outer quadrant of the corner.
	</fo:block>

#### Screenshot of rendered code by Apache FOP 2.0
![][1]

### HTML & CSS rounded corners example

#### Code

	<div style="
		border-style:solid; 
		border-width:10px; 
		border-color:#00f; 
		border-radius:20pt; 
		padding:20pt; 
		text-align:center; 
		margin-bottom:10pt">
		Circular corners are specified when 'border-radius' is set to a single value.  This value is the radius of the outer quadrant of the corner.
	</div>

#### Screenshot of rendered code by Google Chrome
![][2]

## Summary
All in all, this seems like a solid release for Apache FOP, it's nice to see new features being added. I look forward to putting them to work in a future project.

  [1]: /assets/img/apache-fop-rounded-corners.PNG
  [2]: /assets/img/chrome-rounded-corners.PNG
