---
title: "Split Screen Terminals"
date: 2021-04-20T19:26:42-04:00
draft: false
thumbnail: ""
categories:
  - "Terminal Tools"
tags:
  - "screen"
---

Some interesting challenges arise when your local host machine is running Windows, but the application you support runs on one or more linux servers.  As a visual, a typical list of applications open on any given day include: Outlook, SQL Management Studio, Excel, Notepad++, a network tool, and one or more putty sessions.  With all of these applications open during the day, any ability to streamline the workflow is more than welcomed.  

The linux terminal utility called "screen" allows you to create a virtualized sesson that are independent of your connection to server. This can be critical when running a long process that can't be terminated if the remote connection becomes disconnected.  Another great feature is that you can split a terminal window to have multiple smaller terminals within the larger window.  A good analogy is a house window being the terminal, but then splitting the window into glass areas between the window muntins.  Once the screen is split it is possible to run a different terminal command in each screen independently.

![split screens](/static/split_screens.png "image")
