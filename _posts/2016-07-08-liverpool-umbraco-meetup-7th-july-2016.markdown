---
layout: post
title: Liverpool Umbraco Meetup - 7th July 2016
description: First umbraco meetup in over a year, I attended to see whats happening in Umbraco land following this years dev conference "Code Garden".
categories: [Umbraco]
tags: [meetup, Liverpool]
---
First umbraco meetup in over a year, I attended to see whats happening in Umbraco land following this years dev conference "Code Garden".

The meetup hosts where

- Marc Goodson (Head of Development at [Moriyama][1])
- Dan Booth (Senior Backend Developer at [Ph.Creative][2])
- Kevin Jump (of uSync fame / infamy at [Jumoo][3])

The meetup was really 2 talks, the first being the Marc and Kev show, giving us an overview of the pre Code Garden retreat that Marc attended and Code Garden itself. The second was from Dan Booth showing his new God mode package.

Here are the highlights

## Umbraco version 8

- Loads of features or breaking changes being held back to go into Umbraco 8
- There is a new memory based cache, say goodbye to our XML based existing one
- Libraries such as Angular 1.2 will be getting updated which will impact the back office and packages

## General Umbraco changes

- New package manager inbound with support for min umbraco version, this may land earlier than v8
- Better support for nuget packages, feature parity with the backoffice packages. You'll be able to add doctypes etc from a nuget package
- 301 redirects will be part of the core, Marc worked on this at the retreat and is currently creating a dashboard for it in the back office. Days of using a package such as 301 URL Tracker appear numbered
- Courier has been vastly improved as part of the UaaS work, now 'rock solid'
- Courier is getting replaced despite being 'rock solid' with Umbraco Deploy a ground up rewrite of Courier, more like a Umbraco CLI than anything else
- New healthcheck coming as part of 7.5 will do checks on the site similar to uGoLive used to on v6, you'll be able to extend it with your own checks

## Umbraco as a Service

- New pricing structure
- Now[ starts at 25 euros][4]
- The Pro package should now be 40ish Euros despite the site still saying 400
- Umbraco planning to get 1 in 10 Umbraco installations on UaaS by 2021
- If you have a complex Umbraco installation UaaS isn't for you
- UaaS requires your project to be setup in a specific way to work, so you can't just throw an existing site on there and have it work

## Umbraco God Mode package by Dan Booth

Dan presented his new package for Umbraco 7.4+ [God Mode][5] here are the highlights

- a Windows Explorer like media browser
- You can see where templates or doctypes are in use, plus many other things
- Inspect your Umbraco installation, see settings from the config files from the package
- View generated models and much more
- Looks really useful for getting to know a new site you've inherited

## How to create your own package tips by Dan

Dan shared some tips on how to create your own packages using Angular 1.2 and Web api within Umbraco

- He has a script for creating both a [nuget and backoffice package][6] checkout the bat file at the link to his Github
- He also said to feel free to look at this code for hints on how to get the tree structure setup and how to call Umbraco, makes it look a bit more accessible than we may have thought

## Code Garden Videos

Perhaps the most important bit for those of us that didn't get to go to Code Garden is the videos of the talks.

- [http://video.twentythree.net/codegarden][7]
- Highlight of the show was Marc's talk on [anti-patterns][8] or how not to do Umbraco in lay mans terms
- The other recommended talk was [Je suis Core][9]

In summary was a good meetup, lots of information to take in. Lets hope the next one is soonish.

  [1]: https://www.moriyama.co.uk/about-us/
  [2]: http://www.ph-creative.com/about/team/
  [3]: http://jumoo.uk/
  [4]: http://umbraco.com/cloud/features-and-pricing/
  [5]: https://github.com/DanDiplo/Umbraco.GodMode
  [6]: https://github.com/DanDiplo/Umbraco.GodMode/tree/master/BuildPackage
  [7]: http://video.twentythree.net/codegarden
  [8]: https://video.twentythree.net/umbraco-anti-patterns
  [9]: https://video.twentythree.net/je-suis-core
