---
title: How to Paste Excel data into SQL Server
date: "2019-10-30T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/paste-excel-into-sql-server/"
category: "Tutorials"
tags:
  - "Excel"
  - "SQL"
  - "Snippets"
description: "How to seed a new table in sql server with copied data from excel."
socialImage: "/media/excel.png"
---
When prototyping or creating new tables in excel, often times I'm creating the table to hold data that comes from excel. Thankfully, there is a really nice trick to seed the data from excel into your table without having to do any type of import process. 

First, you must make sure that your table columns line up exactly with the columns you have in excel.
 
>The column names don't need to be the same, just the data.

Next, open up SQL Server and go to the "Edit Top 200" mode. Go back to excel and copy all the data. Now back in sql Server,paste the data in the first field. Depending on the amount, it may take a while. Save the file and you are good to go!

I've used this trick many times to get sample data in to newly created tables.