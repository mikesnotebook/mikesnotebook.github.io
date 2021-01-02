---
layout: page
title: "Identify and connect to a data source"
permalink: /da-100/connect/
---

Seems simple enough, right? Get data --> pick your data source, go through the wizard.

There’s so much packed into that one phrase, however, such as knowledge of csv, xml, json, SQL, Azure, etc. 

Let’s start with CSV. This has been around for decades, so there’s no shortage of info about it on web already. Here are a few suggested tasks:
- Create your own simple CSV file with notepad to store a few columns and rows of any data you’d like, perhaps the following if you’re not feeling creative: id, name, address, zip code. For now, don’t include column names, just a few rows of data, and import this into a dataset using power bi
- Look at the result, especially pay attention to the field names and data types. Change one of the zip codes to have a leading zero and do it again. Any changes?
- Change the csv so that the first row has the column names, and import it again.
- In one of the address values, add a comma, like:   
  10 main, apt 1
- Import it again. What happens and why?
- Go google “csv text qualifiers” and read up on this, and then fix the csv
- If you used double quotes for the text qualifiers, change one of the names to: Dwayne “The Rock” Johnson, and try the import again.
- Read more about csv and text qualifiers until you understand strategies for dealing with this.

XML
- Go read up on why XML exists to begin with. What problem(s) did it solve?
- Read up on the basic syntax of XML. What is well formed XML vs Valid XML?
- Enter the exact same data as you used for the CSV into your own xml file, and import it. (again, just use notepad). 
- Here’s some sample xml from Microsoft. Copy it into a file, and import it:
  - https://docs.microsoft.com/en-us/previous-versions/windows/desktop/ms762271(v=vs.85)
- Here’s another:
  - https://www.xmlfiles.com/examples/plant-catalog/

JSON
- Go read up on why JSON exists to begin with. What problem(s) did it solve?
- Read up on the basic syntax of JSON. 
- Enter the exact same data as you used for the CSV into your own json file, and import it. (again, just use notepad). 
- Go to data.gov, and do a search for a government related topic. On the left side, scroll down and filter the results for json. Find and download a json file, then import it into Power BI.

SQL
- Why is having a SQL database better than just a few xml or json files? 
- What is the difference between SQL and Microsoft Access?
- What is a SQL Server vs a SQL database?
- What is a SQL Instance?
- To connect to a database on SQL Server, you’ll need to have credentials. What is the difference between using SQL authentication vs Windows Authentication?
- What is the difference between using Azure SQL and SQL Server?
- Go download and install SQL Express, as well as a sample database or two, such as AdventureWorks and AdventureWorksDW
- Import data from your database into a Power BI Model. 

Side bar:  
Working with databases requires you to understand basic database concepts. So go read up and work with the following until you’re ok with these concepts:
- Tables
- Database normalization and the basics of normal form
- Relationships
- Primary and foreign keys

Let me remind you of something I wrote at this beginning: this is the long road to preparing for the DA-100 exam. The four bullet points above are the subjects of countless articles, and even books and courses. (just search on amazon for “database design in books”). If you skim one article on this and then move on, you’ll struggle in later sections on star schemas, and you’ll likely have more difficulty understanding many DAX functions. So here’s a suggested set of basic exercises to get more comfortable with these items, though again, this topic is large enough to warrant doing more than a couple basic exercises:
- Think of any topic that interests you. Perhaps a hobby or something with work. If you’re out of ideas, here’s a topic: “Power BI Resources”
- Based on what you read about tables, identify two tables you can create (if your example only requires one table, either read more about table design to determine a second table, or pick a different topic.). In my example, the two tables will be: “Topics” and “Resources”, where topics will be the list of exam topics, and Resources will be a list of web pages, books, etc., where each resource is connected to a single topic.
- Create the tables in your SQL database, including a primary key in each table, and add some data
- Before creating any database relationships, import the data into Power BI, and create a functional report with data from both tables (you’ll need to configure a relationship in power bi)
- Go back to the database, and create a relationship in the database (you’ll need a foreign key). Import it again into a new report. Did anything different happen?
- In this scenario, what if a Resource applied to more than one topic? With the current design, that’s not possible, as each resource is only associated with a single topic, unless you add the resource multiple times. So go read up on “many to many” relationships, and create a new database with three tables that allows a Topic to be associated with many resources, and a single resource to be associated with many topics. And of course, create a report using these tables.

Web:
It’s simple to import data from tables on web pages, and Wikipedia has a lot of tables. 
- Find the Wikipedia page for the list of countries by size. Import this into a Power BI model and create a report.
- Find other tables on Wikipedia and create a few more reports. If you’re out of ideas, go to Google and type in: “Wikipedia list of” and check out the Google auto-suggest options.

