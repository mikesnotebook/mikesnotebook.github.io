---
layout: page
title: "Configure table and column properties"
permalink: /da-100/table_properties/
---

Remember, the goal of configuring the model is to make it as easy as possible to build reports later on, this means that table and column names should be good, data types should be correct, formatting should have good defaults, etc. There are a number of various properties, but let me focus on one common source of confusion: Formatting, or, what should happen in Power Query vs the model.

Let's consider a date: 6/1/2021. Here in the US, this is interpreted as June 1st, 2021. In other parts of the world, it is January 6th, 2021. We could also write it a number of other ways, such as 2021-06-01, or Jun 6, 21, etc. All of these various ways of writing the date are all various formats. While I couldn't find documentation for how Power BI stores dates, Excel stores dates as the number of days since January 1st, 1900, and times are a fractional compononent of the date. So in Excel, 6/1/2021 is 44348, and 6/1/2021 6:21 AM is 44348.26485. To these tools, 44348 is the real date, not 6/1/2021. 6/1/2021 is the formatted string that is displayed to the user. 

What is the significance of this? If the tool has the actual date value, 44348, it can do date calculations with this value. It can also format it however you'd like. If, however, the system doesn't have this date value, and instead only has the formatted string, such as 6/1/2021, then the tool would need to convert it to a date to be able to do any calculations or to be able to change the format of the date.

Again, what's the significance? When we load data in into the model, we want to be sure that date fields actually are a date data-type. I hope I didn't confuse you with the comments above about how excel stores the number. We certainly don't want to see anything like 44348 in the model. I was trying to emphasize that fields configured as date data-types are stored differently and have different capabliities than a text field that is storing a value of "6/1/2021". If we have date values, we can then use the column properties to output whatever format is needed. So, given a CSV file with a column of dates, the process we want to follow is:

1. Use Power Query to load the date column into the model as a date field. Formatting at this stage is irrelevent.
2. Once the date field is in the model as a date data type, use the column properties to format it as desired.

The above conversation also applies to numbers. Let's get the appropriate data into the model, and once it's in the model, then we can format it how we would like.

There is one exception to the above: rounding. Going back to the example with time, is there any business requirement that you will need to output the time? Will thre be calculations based on the time? If so, the above explanation applies. But often, reports don't use the time at all. In these cases, it is more efficient to get rid of the time from the model completely, rather than to store it and use formatting to hide the time. More on this in the performance section.

Suggested Excercises:
1. From AdventureWorksDW, import the DimCustomer table, taking the defaults. Observe the behavior when you add Customerkey to table in report view. 
2. Change the "Default summarization", or "Summarization" property of CustomerKey to "don't summarize", and add CustomerKey to another new table, and observe the difference.
3. Import a table with both month name and month number to the model, and output a table that displays month name, sorted by month number. 
4. Using AdventureWorksDW, produce a table that has sales by product category. Make the necessary changes to output the categories in the following order: Bikes, Components, Accessories, Clothing
5. Create and import a table with the following columns and values. Then create a map, and change the Location column from a Data Category of State/Province to City and observe the results:

    |Location   | Amount       |
    | :------------- || :------------- |
    |New York   |  1  |
    |Washington |  2  |
    |Oklahoma   |  3  |
    |California |  4  |

6. Import the DimDate table, and experiment with various date formats for the date field




