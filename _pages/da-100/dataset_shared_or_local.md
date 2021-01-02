---
layout: page
title: "Select a shared dataset or create a local dataset"
permalink: /da-100/dataset_shared_or_local/
---

Imagine that you’ve been in charge of a company’s data warehouse and reports for years. While the memories aren’t exactly pleasant of the countless meetings it required to define things like “active projects”, you take great pride in how clean the data warehouse is, and how well things are defined (mostly). And now imagine attending a meeting where it is announced that employees will get access to Power BI, and will be able to connect to whatever database they want, create any calculations they want, name things whatever they want, and can then can share out the reports they make with executives who will make critical business decisions based on all of this. 

- While thinking of what your mood would be in the above scenario, go read up on shared datasets
- Create a shared dataset, and create a report that uses one

In case my point wasn't clear, creating reports based on shared datasets should be absolutely common in most organizations. If multiple reports are being made to report on various attributes of the project management system, all reports should use the same field names, same calculations, etc. Shared datasets allow us to accomplish this without copying the same code to multiple reports. 

Shared datasets also allow a separations of roles, allowing one person or small team to maintain the master report with the dataset, while others simply create reports that connect to and use that dataset. The skill level required for these latter folks is far less, which brings the goal of self service BI closer to reality. 

Sidebar: in case you didn't get my reference to the confusion around "active projects", this is a real thing in project management systems. It's a common requirement on project management dashbaords to only show details for active projects, but the definition of what consitutes an active project will change depending on the audience. Is the project that consumed a large amount of budget but was recently cancelled an active project? One one hand, no, it's cancelled. On the other hand, many users will want that project to still show up on reports due to the fact that money was spent. 