---
layout: post
title: Azure Resource Manager - ARM Templates, MS Build Update
description: The latest news on ARM Templates from MS Build 2020
categories: [Azure]
tags: [MS Build, ARM]
---

I attended (watched) the talk on "Infrastructure as code - build Azure applications with ARM templates" at MS Build last night presented by Brian Moore (Program Manager at Microsoft). The talk was focused on what's new with ARM. 

At the start of the talk Brian signposted a previous talk from Ignite that went into a bit more detail (being 47 mins long vs this 30 min session)
[ARM Ignite 19](https://aka.ms/ArmIgnite19). 

In this post I'll be giving a brief overview of the topics he discussed with links to further reading.

## Deployment Scripts

Deployment scripts let you perform custom steps with Powershell or Bash scripts that you can't do in ARM templates. Brian said the intention was for them to cover the last mile in a deployment. They support both Azure Powershell and AZ CLI. Now in public preview for you to try out. 

[read more about ARM deployment scripts](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-deployment-script)

## Azure Resource Manager Template Testing Toolkit (arm-ttk)

Arm-ttk is a set of tests that will check your ARM template code or sets of templates for best practices. You can extend it and add your own tests, in all it looks like a good addition to a developers toolkit and I can see it being useful in pipelines to spot potential errors before deployments.

[Github docs for arm-ttk](https://github.com/Azure/arm-ttk)

## ARM template deployment what-if

Currently in preview, what-if lets you see what changes your ARM templates will trigger should you deploy your templates. Sounds a lot like Terraform Plan, with the advantage that rather than being run against a state file, it is looking at the current resources in Azure. Brian mentioned that you'll be able to output the response of what-if to a json file, which opens up the possibility of running Unit Tests against it using Pester or your favourite testing framework.

[read more about ARM template what-if operation](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-deploy-what-if?tabs=azure-powershell)

## ARM Template Specs

ARM template specs are new and allow you to bundle together ARM templates and their supporting files into another ARM resource that can be re-used within an ARM template private registry and shared with others. If this sounds a lot like Blueprints you'd be right, Brian said the intention long-term was to migrate people from blueprints to template specs. Details on this are pretty light at the moment, expect documentation to follow in the coming weeks.

## ARM Language Revision

The final bit of news was pretty big, there are plans afoot to revise the ARM language as we know it. After much feedback on how using JSON as a programming language really wasn't cutting it, when you compared with HashiCorp's HCL as used in Terraform. The most common complaints being about modularising code for maximum re-use and struggling working with multiple files.

To address this the new language will have first class support for modularisation and working with multiple files. It will have transparent abstraction in Azure, they don't want it to get too far away from a native experience. JSON is being ditched, and no YAML isn't going to replace it. The new language won't be copying Terraform and using a state file, being a native solution it doesn't need it. The what-if operation will continue to serve that purpose.

The initial 0.1 release is expected in 2-3 months so keep your eye out for it. Short term this new language will exist alongside legacy ARM, it'll likely be many years before they drop support for the JSON format. All in all, exciting times for ARM template developers.
