---
title: SharePoint Internal Names and Power Apps
layout: single
date: 2020-12-29 12:53:00 -0500
categories: [Power Apps, SharePoint]
tags: [power apps,sharepoint]     # TAG names should always be lowercase
---

# Finding the Correct Field Names for the SortByColumns Function

A common error folks run into with the SortByColumns function is: "The specified column does not exist". Following is the long answer on why this happens, and how to resolve it.

All SharePoint fields have two names, the display name and the “internal name”. When you create a field that has a name of one word, the internal name will be the same:

Field: bridge  
Internal name: bridge

If the name you provide when creating the field has spaces, the internal name will have \_x0020\_ instead of the spaces:
Field: Bridge Name  
Internal Name: Bridge_x0020_Name

*Note: the above answer about spaces will change depending on how the field is created. Some methods in SharePoint will simply eliminate the space from the internal name, other methods will insert the \_x0020\_.*

If you rename a field, the internal name does not change:

Original Field Name: bridge  
Original Internal Name: bridge  
Current Field Name after rename: tunnel  
Current Internal name after rename: bridge

And, a few of the Power Apps functions use the internal name, not the display name. 

So when you changed Title to BridgeName, the display name was BridgeName, but the internal name was still Title. We can’t change this, this is just how SharePoint works. And while most places in PowerApps will use the Display Name, a few, such as the SortByColumns, will use the internal name. 

The docs for this function are here:  
https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/functions/function-sort

For the column name argument, all it says is:
“ColumnName(s) - Required. The column names to sort on, as strings.”

It doesn’t say anything about the internal name. But, there’s also a note:
“Note: For SharePoint and Excel data sources that contain column names with spaces, specify each space as "\_x0020\_". For example, specify "Column Name" as "Column_x0020_Name".”

It points out the issue with spaces, which is the hint to us that it is using internal names, not display names. Though it neglects to actually mention internal names or field renames. 

So how does one determine the internal name? There are a number of different methods, but one method is available within Power Apps. Add an edit form, and add the fields in question to the form. Then, with the form selected, click on “edit fields” in the panel on the right, and if needed, expand each field. The details section for each field will display the internal name:.

![Power Apps edit fields link](/assets/img/screenshots/20201229_1.png)  
![Power Apps edit fields link](/assets/img/screenshots/20201229_2.png)  
![Power Apps edit fields link](/assets/img/screenshots/20201229_3.png)
                            



