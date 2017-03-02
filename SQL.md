---
layout: page
title: SQL
---
## SQL
Rahul A, Senior Statistical Analyst at Walmart Labs
Written Jan 6
You want to learn SQL. Here is a crashcourse..

I have read somewhere that an analyst who doesn’t know SQL is not worth his salt. And that seems true to me in every sense of the world. So congrats on making the decision to start up with it.

Now the best way to learn SQL will be to get your hands dirty with it. I will advice against using the web based recipes for SQL since you cannot use your own data with those. I will also advice you to go with learning the mySQL flavor of SQL which is:

Open Source : The best kind of source :)
Easy to setup in your own laptop
Has a great client named mySQL Workbench.
Now to get you up and running here are some pointers on how to get setup with mySQL.

You can download mySQL for your particular system (MACOSX, Linux, Windows) from:

Download MySQL Community Server

Once you get that running install the mySQL Workbench to make your life easier:

Download MySQL Workbench

Get connected with the mySQL Server using the mySQL Workbench.

The above steps might take some time to get right and you might need to go back a couple of times to Google and Stack Exchange for getting it to work.

And then try installing some data for yourself to practice.

Now if you have your own data to work. Then good and fine. You can upload it into various tables using these following commands:

CREATE TABLE your_data (col1 integer, col2 varchar(255), col3 double)
 
LOAD DATA LOCAL INFILE '/datapath/data.csv'
INTO TABLE your_data 
FIELDS TERMINATED BY ',' 
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
Otherwise you can use the Sakila database which you can install using the following three steps:

Other MySQL Documentation : Search for Sakila and download the zip file
Unzip the file.
Goto mySQL Workbench and select File >> Run SQL Script >> select location of sakila-db/sakila-schema.sql
Goto mySQL Workbench and select File >> Run SQL Script >> select location of sakila-db/sakila-data.sql
Now you have some data on with you. Now we have learned on how to setup a SQL server and we should start with writing some queries:

Try to understand the Schema of the Sakila Database using the schema document and mySQL Workbench. The schema document is here : Sakila Sample Database :: 5 Structure
Now the basic syntax of most mySQL queries is:
SELECT col1, 
sum(col2) as col2sum ,
avg(col3) as col3avg
FROM table_name 
WHERE col4 = 'some_value'
GROUP BY col1 
ORDER BY col2sum DESC;
The above query will help you with most of the simple things you want to find in a database. For example: Lets say you wanted to find out how differently censor rated movies are timed differently, you can use :
SELECT rating, avg(length) as length_avg FROM sakila.film group by rating order by length_avg desc;


