---
layout: post
title: Markdown - Write More
description: What is Markdown and why should we use it to write content for our web sites? This post looks at the basics and how you can use it in Umbraco and WordPress.
categories: [Umbraco]
tags: [Umbraco 6, Markdown]
---
Background
----------
Markdown was created by John Gruber at Daring Fireball as a text-to-HTML conversion tool for web writers. 

>The overriding design goal for Markdown's formatting syntax is to make it as readable as possible. The idea is that a Markdown-formatted document should be publishable as-is, as plain text, without looking like it's been marked up with tags or formatting instructions.

So what does that mean to you?
------------------------------

### Your Content Managed Website 
When writing your blog posts or any other content for that matter, most CMS's like Umbraco rely on a rich text editor that behind the scenes creates HTML. For the most part this approach works, however it can be a little fragile especially when you cut and paste text or hit enter a few times to create space between content, which can insert unwanted empty paragraph tags or completely break your page layout. At which point you either switch to the HTML view and correct it, or call up your web developer and ask them to.

Switching to markdown makes this much more robust and gives you more control as the writer, letting you concentrate on what matters most, writing content. 

### Removing Distractions
Modern Word processors such as Microsoft Word and Google Docs get in the way of writing, controversial I know, but it's true. They show you errors as you make them, interrupting you to inform you that your grammatical structure is wrong, you've spelt something wrong or you haven't, but Word insists on using the US English dictionary and tells you to replace your s with z. So you stop, correct the mistake and lose your train of thought resulting in you actually writing less.

By moving to an editor that has none of these things you'll improve the amount that you write and prevent writers block from creeping in. It means a slight change to your work flow, you'll have to check for spelling errors and grammatical errors after you've written your content, which I believe this leads to better quality content as you are forced to review your work rather than assuming that Word's auto-correct got everything right. I like to think of it as a built in editorial process.

### Learning curve
The downside to this new world of free-flowing writing is that you have to learn so markdown, the good news is that it's pretty trivial and won't take you long. You can head over to [daringfireball](http://daringfireball.net/projects/markdown/syntax) for a full overview, with some highlights below:

## Example

	Level 1 Heading
	====================

	Level 2 Heading
	---------------------

	Some regular paragraph text.

	### Level 3 Heading

	> This is a block-quote.
	> 
	> This is the 2nd paragraph in the block-quote.
	>
	> ## This is an Level 2 heading in a block-quote

	Example Bold / Italic

	This is *italic*

	This is **bold**

	Lists

	* List Item 1
	* List Item 2
	* List Item 3

## Ok, you want to try it out, how do you do that?

### Windows

[MarkdownPad](http://markdownpad.com/) is free, has a split screen approach showing your markdown on the left and the finished page on the right. You could of course just use your favourite text editor such as Notepad, TextPad or Sublime Text, these markdown specific editors just make it easier to see how you final page will look.


### Mac

[Mou](http://www.mouapp.com) has a similar approach to MarkdownPad and is also free.

### iPad

[Editorial](http://omz-software.com/editorial/), doesn't do split screen but given the screen size of an iPad I'm not surprised. It costs $4.99 and has an best of 2013 app store award. 

### Android

[JotterPad X](http://2appstudio.com/jotterpadx/) seems to be the best option on Android, like Editorial it doesn't do split screen. Looks likes it free to download with in-app purchases.

### Web

[Dillinger.io](http://dillinger.io/) it's a free cloud-enabled markdown editor that works with Dropbox, GitHub and Google Drive.

## How Do I Get Markdown Content On My Site?

Install one of the plug-ins below and copy and paste it in. Or you can write directly in Umbraco (or WordPress).

### Umbraco CMS Plug-in (Developer Notes)
Umbraco requires a plug-in to enable a new markdown data type, you can find it on [our.umbraco.org](http://our.umbraco.org/projects/backoffice-extensions/markdown-editor) or you can install it via the umbraco back office

* Go to Developer -> Packages -> Umbraco package Repository
* Search for markdown and install the markdown editor

One thing to note when outputting the new datatype is that you'll need to wrap it in a @Html.Raw to have the HTML display correctly on the page. 

### WordPress CMS Plug-in
WordPress.com supports it out of the box, you just need to enable it.

* Go to Settings -> Writing in your dashboard and check the box "Use Markdown for posts and pages."

WordPress.org standalone web installations need to install a markdown plug-in like Jetpack Markdown which is in the WordPress.org plug-in directory.

When writing your posts switch to the Text editor (Text tab) for best results.

#### Markdown resources

* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)