---
title: Apps Script
description: Google Apps Script is a versatile, easy way to add advanced functions to Sheets, and scripts activities across Google apps.
published: true
date: 2022-07-11T15:10:04.252Z
tags: 
editor: markdown
dateCreated: 2022-07-11T15:10:04.252Z
---

# Google Apps Script

Google Apps Script is “a cloud-based JavaScript platform that lets you integrate with and automate tasks across Google products.” It's free, powerful, and flexible, making it a great choice for automations of all kinds. Apps Script can be tricky to get the hang of at first as it's grown and changed a lot over the years, but once you have a solid foundation, you'll be scripting everything with ease.

## Apps Script Types
Apps Scripts can come in a few different types. The two most important types are `standalone` and `container-bound` scripts.

### Standalone Scripts
Standalone scripts are created at `script.google.com`. They can be bound to a [dedicated Google Cloud Platform project](https://developers.google.com/apps-script/guides/cloud-platform-projects) to take advantage of things like higher quota limits on the project or OAuth verification.

### Container-bound scripts
[Container-bound scripts](https://developers.google.com/apps-script/guides/bound) are created from a Google application like Sheets or Slides. For example, if you create a script directly from Sheets, you have created a container-bound script. Bound scripts behave similarly to standalone scripts, but with a few exceptions. 

They gain a [few new functions](https://developers.google.com/apps-script/guides/bound#special_methods), such as creating menus or getting file information without needing to specify the file ID. A common special feature of bound scripts is creating a [custom function](https://developers.google.com/apps-script/guides/sheets/functions) to use in Google Sheets.

### Script permissions
Standalone scripts behave like Drive files — you can share them with specific people, and you'll see them appear in Google Drive.

Bound scripts do not appear in Drive. Only editors of a file can run a bound script. Anyone with the ability to copy the file can read and run the script on their copy.

  

## Scopes & Security problems
Permissions, scopes, and security questions are common problems can be tricky to debug. Keep in mind a few things:
	- When creating an Apps Script