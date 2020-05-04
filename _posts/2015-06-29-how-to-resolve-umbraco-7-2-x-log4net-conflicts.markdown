---
layout: post
title: How to resolve Umbraco 7.2.x log4net conflicts
description: How to fix the yellow screen of death caused by Umbraco and Log4net conflicts and packages that use a newer version of log4net.
categories: [Umbraco]
tags: [ASP.net MVC 4, log4net, Umbraco 7]
---
Issue
-----

After installing a package that uses a newer version of Log4net, Umbraco fails to start and you get the yellow screen of death.

![][2]

Steps to recreate
-----------------
1. With a working copy of Umbraco 7.2.x install a NuGet package that requires Log4net 2.0.3 such as Google.Apis.Customsearch.v1
2. Following installation of the package build and run site
3. Site fails with error: "Could not load file or assembly 'log4net, Version=1.2.11.0, Culture=neutral, PublicKeyToken=null' or one of its dependencies."

Steps to correct
----------------

1. Download 7.2.5 zip and extract the log4net dll
    - Rename the dll to log4net.1.2.11.0.dll
    - Place it in a folder in your solution, mine is named Dependencies
    - Include in project
    - Go to dll properties
    - Set build action to "None"
    - Set Copy to Output Directory to "Copy if newer"
    - ![][1]
	
2. add the following to the web.config, be sure to reference the bin directory as that's were your new folder will be copied at build time.

        <assemblyBinding>
            <dependentAssembly>
                <assemblyIdentity name="log4net" />
                <codeBase version="1.2.11.0" href="bin/Dependencies/log4net.1.2.11.0.dll" />
            </dependentAssembly>
        </assemblyBinding>


3. Build the solution, and run, your site should now be back to normal.

This enables Umbraco to use it's preferred version of Log4net (1.2.11.0) whilst your other packages use Log4net 2.0.3.

[1]: /assets/img/log4net-dll-properties.PNG
[2]: /assets/img/log4net-yellow-screen-of-death.png