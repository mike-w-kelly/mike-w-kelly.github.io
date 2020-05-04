---
layout: post
title: ReactJS for .Net Developers at Manchester .Net meetup
description: I went along to the my first Manchester .Net meetup, for a talk by Macs Dickinson about ReactJS for ASP.net MVC developers.
categories: [Code]
tags: [ASP.net MVC 4, meetup, manchester, reactjs]
---
I went along to the my first Manchester .Net meetup, which has now joined forces with another group to become the [Windows Platform User Group North West](http://wpug.uk/), a sort of super meetup group with attendance to match. 

The meeting space at Spaceport was full to bursting on a humid night in the centre of Manchester. The hosts had laid on beer and soft drinks for everyone and the event sponsors [Evolution Recruitment](http://www.evolutionjobs.co.uk/) provided Domino's pizza for all, which was a nice touch.

The guest speaker tonight was [Macs Dickenson](http://www.macsdickinson.com), who was engaging and enthusiastic about React.js for ASP.Net MVC developers. He walked us through some basic code examples before showing how it fitted into the .Net workflow with Visual Studio.

Key points were
-------------------

- ReactJS can easily slot into a Asp.net MVC workflow, it replaces most of the Razor code we'd normally write
- [ReactJ.net](http://reactjs.net/) is a package that takes much of the hard work out the integration and includes a HTML helper to server side render ReactJS to work around the normal first load penalty you get with a JavaScript rendered HTML page
- ReactJS isn't a framework like Angular which replaces large parts of your stack, it does  a small number of things and works with the server side framework. They are trying to solve different problems
- ReactJS has a relatively small learning curve, you could easily know enough in a weekend to be productive with it
- React has one way data binding with an immutable state, basically changes to state are pushed to the view and react updates based on a diff between the DOM and it's virtual DOM, when a change is triggered by an action it calls a service which updates the state which then updates the view. Much simpler than say Kockout.js or Angular 1.x
- There is no built in AJAX functionality, that needs other NPM packages Macs said he used the native [Fetch API](https://developer.mozilla.org/en/docs/Web/API/Fetch_API) with a [polyfill from Github](https://github.com/github/fetch)
- Component / Modular approach to UI development, should result it better, more testable code that can be reused across projects

Summary
--------
Good talk, very useful for getting your head round the basic concepts of ReactJS and how to use with ASP.net MVC and the new ASP.net Core. I for one will likely be trying it in my next project. 

I was most disappointed I didn't win the raffle with the first prize being a Xbox One(sy), oh well maybe next time. 

Date and Time
-------------
26th July 2016 @ 6:30 - 9pm

Guest speaker
-------------
[Macs Dickenson](http://www.macsdickinson.com)

Venue
------
SpaceportX

Hosts
-----
- Mike Irving
- Oli Newsham
- Rick Garner
- Jason Holloway

Pizza and Beer
--------------
- Evolution Recruitment

Raffle Prizes
----------------
- Xbox One(sy)
- JetBrains licences


Links
-----
Talk details and slides

- [http://www.macsdickinson.com/react-for-dotnet-devs/](http://www.macsdickinson.com/react-for-dotnet-devs/)

Github with code samples from the talk

- [https://github.com/MacsDickinson/ReactForNetDevs](https://github.com/MacsDickinson/ReactForNetDevs)