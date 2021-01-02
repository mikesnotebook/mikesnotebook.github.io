---
layout: page
title: "Combine queries"
permalink: /da-100/combine_queries/
---

Merges, appending, and combining files. 

Remember, our goal is a beautiful star schema. Opening the table relationship view and seeing a star schema is like sitting down in front of a fireplace in the winter, with a good beverage and a nice blanket. Don’t believe me? Work on a project with a disaster of a data model for a month or two, and then return to a project based on a beautiful star schema. You’ll feel the stress and tension lift off of you. 

So here’s a very simple and common example: Imagine a database that has an OrderHeader and OrderDetails table. The header table who placed the order and when, the details has the products and quantities. This is pretty simple, but this is not a star schema. 

Here’s an article from the Kimball group (the group behind the definitive books on data warehousing) that covers this common design: https://www.kimballgroup.com/2007/10/design-tip-95-patterns-to-avoid-when-modeling-headerline-item-transactions/

Their solution? A star schema. How do you use power query to get two tables and turn them into a single fact table? Merge. 

Suggested exercise for merging:  
Microsoft provides examples of a transaction database and a data warehouse with adentureworks and adventureworksdw. Take a look at the schema of the sales tables in AdventureWorks, and use Power Query to reproduce the structure you find in the FactInternetSales table in AdventureWorksDW
