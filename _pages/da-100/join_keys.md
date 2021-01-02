---
layout: page
title: "Identify and create appropriate keys for joins "
permalink: /da-100/join_keys/
---

Tables will sometimes use two or more fields as the primary key. Note, this is NOT saying that tables will have two primary keys, but there are two fields working together to act as a single primary key. Look at the following sample orders table:

|Order |ID	|Line Number	|Other fields|
| :------------- | :------------- | :------------- | :------------- |
|1000	|1	|A | |
|1000	|2	|B | |
|1001	|1	|c | |


In the above orders table, the primary key is not Order ID, as each order has multiple line items and so the order id is repeated. (if someone orders socks and a shirt, that’s two line items. Both items are placed in the same order, so the table would have two rows, each with the same order id, but with different line numbers). So in this table, the combination of Order ID and Line Number would be unique, and therefore could be used as the primary key.
What’s the issue with Power BI? Power BI only supports single fields when creating a relationship between tables. So the solution would be to add a new calculated field to the above table that concatenates the Order ID and Line Number, and use that to join:

|Order_Key	|Other fields |
| :------------- | :------------- | 
|1000_1	|A |
|1000_2	|B |
|1001_1	|c |

To read more about how and why multiple columns are used in a primary key, go search for and read up on “composite primary keys”.



