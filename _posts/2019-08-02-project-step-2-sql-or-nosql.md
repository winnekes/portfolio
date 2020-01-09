---
layout: post
title: "Project step #2: SQL or NoSQL?"
date: 2019-08-12
description: "An attempt to defend my choice in database type."
category: blog
tag: 
- simplyshift
- web development
- coding
- project planning
- databases
- nosql
- sql
---
<figure>
	<img src="../assets/images/posts/database_drawers_organising.jpg">
</figure>

For the last week I have been trying to choose between different database types. Here is a list of just a few related posts on this topic that I checked out:

* <a href="https://www.educba.com/mysql-vs-nosql/" target="_blank">MySQL vs NoSQL</a>
* <a href="https://blog.panoply.io/postgresql-vs-mongodb" target="_blank">PostgreSQL Vs. MongoDB</a>
* <a href="https://blog.cloud66.com/3-tips-for-selecting-the-right-database-for-your-app/" target="_blank">3 Tips for Selecting the Right Database for your App</a>
* *and many more*

I might be a lot smarter now after learning the differences between SQL and NoSQL and figuring out the steps to take to choose the appropriate type for your project but it is somehow not making it easier for me to make a decision.

### Things to consider before making my decision

* Structure of my data
* Scalability

I am not going to talk about estimating the size of your future database as that is something I still need to research. For my project the size of my data is negligible and any type of database should be able to handle a couple of GB of data.

---

## Comparing SQL vs. NoSQL 

|               | SQL                                     	| NoSQL                                     |
|:--------------|:-----------------------------------------:|------------------------------------------:|
| Type         	| relational database                      	| based on documents or key-value pairs 	|
|----
| Scalability  	| Vertical scalable                        	| horizontal scalable                     	|
|              	| = scalable by increasing  RAM, SSD or CPU | = scalable by just adding servers 		|
|----
| Data storage 	| data is stored in tables  				| data is stored in JSON-like documents   	|   
|              	| (rigid structure and fixed data types)   	| (unstructured, flexible)  				|
|----
{: rules="groups"}

---

### Code snippet for SQL

Get all the users in the table “users”:

```sql
SELECT *
FROM users;
```

Add a new user to the table:
```sql
INSERT INTO users(user_id, age, first_name)
VALUES ('001', 28,"Simona");
```

---

### Code snippet for NoSQL

Get all the users in the document “users”:
```js
db.users.find()
```

Add a new user to the list of users:

```js
db.users.insert(
  { user_id: "001", age: 28, first_name: "Simona" }
)
```
  

---

## Why I have chosen to go with MongoDB (NoSQL) 

To be completely honest: I know SQL, I can already work with relational databases, I've always understood their concepts of tables, foreign keys and joins. But I have never tried any alternatives to MySQL or even bothered to inform myself more. So I really want to tackle something new and understand both SQL and NoSQL in depth. 

And if I'm going with NoSQL then I'm choosing MongoDB. MongoDB is one of the most popular one among all the NoSQL databases, so I assume there to be a great community established with lots of resource materials and instructions available. 

### Data structure

I assume that the data I will be handling will be very dynamic and will change constantly. I don't have a clear idea yet on how all that data will be 
structured. With MongoDB I do not need to develop a database model before I can actually create the database. I can work on my structure while using the data at the same time, which gives me the flexibility I need for now. 

### Scalability

I don’t fully understand the difference between vertical and horizontal scalability yet (and what is autosharding?) but from what I did understand is that document-oriented databases are easier equipped when it comes to dealing with big data and constant data changes right from the get go. And adding servers to handle increased amounts of data sounds much simpler than actually having to increase computer components like you’d have to do with SQL.

---

**Next up**: what language(s) to use for SimplyShift? 