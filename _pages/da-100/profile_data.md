---
layout: page
title: "Profile the data"
permalink: /da-100/profile_data/
---

Docs on this are here:  
https://docs.microsoft.com/en-us/learn/modules/clean-data-power-bi/6-profile-data

This is one of those units that’s pretty simple…if you understand the basics mentioned in other sections, such as tables and data types, as well as if you understand common scenarios with data. 

For example, newbies imagine that companies have pristine databases that were designed and maintained by professionals and that follow best practices in all situations. 

In short, this doesn’t happen. Companies have bought or built a variety of systems over the years, and customized each in ways that weren’t originally envisioned, and then the data from all those systems is being merged together in one data warehouse. It’s really pretty impressive that this sort of thing works at all. 

Here’s my favorite example of this: I helped migrate data from a company database years ago, and noticed that some of the address fields had phone numbers or other things that were not addresses. There was no technical reason for this, and so I went and spoke to the users. They said that they often needed to do things like enter a second phone number for a contact or the name of a second contact, but as the system didn’t allow it they put in any empty field such as the Address Line 2 field. From a user perspective, this worked just fine, as when they pulled up the record on screen they could easily find the phone number. This system had been in use for years, and the users didn’t mind as it worked for them. From a data perspective, this was appalling, as the infrequently used fields held either that data, or other random data based on where the user chose to click to enter something else. 

This example is clearly an outlier, but it’s common to find things like companies entered multiple times with different spellings, or even states entered with different abbreviations (PA, P.A., PA., Penn, etc).

So how do you use these tools in the real world? Step one is to know your data. From a technical level of data types and constraints, to the business level of understanding what kind of values to expect. If you know that, then these tools become helpful. 

Of course, there’s a chance that someone gets to work on a system where all the data is perfect and where there are no issues, ever, and that person will not understand the need for these tools.  If that’s you, congrats, but I kind of feel sorry for you due to the huge shock you’re going to face when you shift jobs. 
