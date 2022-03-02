---
title: Google Contacts
description: All my odds and ends about Google Contacts
published: true
date: 2022-03-02T23:12:47.543Z
tags: 
editor: markdown
dateCreated: 2022-03-02T17:14:16.048Z
---

# Google Contacts

## Names and profile info
Names and profile info a lot trickier than it first appears in Google. First, there are two public APIs — the Admin Directory API and the People API. The Admin Directory API is straightforward — it updates what you see in the admin console. However, what you see in the admin console is not what you get in the products! There are multiple other sources of name data.

### Gmail & other contacts
**By default, Gmail stores copies of contacts that you email in Gmail, in [Other Contacts](https://contacts.google.com/other).**

If I'm ian@conjecturaltechnologies.xyz, and I email suzy@conjecturaltechnologies.xyz, I should see Suzy in Other Contacts as well as the Directory. Having two copies of a contact is a recipie for disaster. If somone's name changes (like when they get married), and you update it in the Admin Console, users may not see the change. Sometimes the Other Contact seems to update with the new info but sometimes...it doesn't, and end users need to delete it or edit it. 

If you find that you have an Other Contacts issue with many users, the [People API](https://developers.google.com/people/) supports Other Contacts, and you can use [GAM-ADVXTD3](https://github.com/taers232c/GAMADV-XTD3/wiki) to fix it.

Users can turn this off in Gmail under Settings > General, and admins can use GAM to turn this off in bulk. At time of writing, there is no option in the admin constrol to control this.

### Google Account Personal Info
In one case, I had a user with the correct information in Google Admin and I didn't have them in Other Contacts, but their name was still wrong. The user had to go into their Profile Info > Personal Info and edit their own name. This happened becuase we allow users to set their own name — it won't sync. 

If you disallow users from changing their name (or other profile data) it will reset to the information synced by the admin console. 

You can always view both of the profile data fields API (`gam user user@domain show peopleprofile`)

### Wrap-up
Let's look at the big picture — where can names come from? So far, I've found five places:

- Admin console 
- Contact 
- Domain Shared Contacts
- Other Contact
- User profile (when allowing users to change profile data)

Gmail, and other apps, seem to prioritize Contacts data over other sources, but I can't confirm the exact order of priority.