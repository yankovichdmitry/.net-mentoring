# .NET Mentoring

Table of contents:

- [SQL](#sql)
   - [Basics](#basics)
   - [Transactions](#transactions)
   - [Stored Procedures](#stored-procedures)
   - [JOINs](#joins)
   - [Normalization](#normalization)
   - [SQL databases](#sql-databases)
   - [ACID](#acid)
- [NoSQL](#nosql)
   - [Difference from SQL](#difference-from-sql)
   - [Types of NoSQL databases](#types-of-nosql-databases)
   - [SQL vs NoSQL](#sql-vs-nosql)
   - [NoSQL databases](#nosql-databases)
   - [CAP theorem](#cap-theorem)
- [File Storage](#file-storage)
   - [Amazon S3](#amazon-s3) 
   - [Azure storage](#azure-storage)
   - [File System](#file-system)
   - [Best Practices](#best-practices)
   - [NFS](#nfs)
- [Caching](#caching)
   - [Redis](#redis)
   - [HTTP cache](#http-cache)
   - [In-memory cache](#in-memory-cache)
   - [Warm and cold cache](#warm-and-cold-cache)
- [Session and Cookies](#session-and-cookies)

---

## SQL

##### Books
- “Learning SQL” By Alan Beaulieu;
- "Database System Concepts" Abraham Silberschatz

##### Videos
- [Keys](https://www.youtube.com/playlist?list=PLU9JMEzjCv176mRCXCCijrA5Jl6c9ihMM)
- [SQL Server tutorial for beginners](https://www.youtube.com/playlist?list=PL08903FB7ACA1C2FB)
	
	
##### Courses
- [Course by w3schools](https://www.youtube.com/playlist?list=PLU9JMEzjCv176mRCXCCijrA5Jl6c9ihMM)
- [Course by codeacademy](https://www.codecademy.com/learn/learn-sql)

### Basics

##### Videos
- [SQL Server Basics](https://www.youtube.com/playlist?list=PLU9JMEzjCv14f3cWDhubPaddxRvx1reKR) 

### Transactions

##### Videos:
- [Transactions in sql server](https://www.youtube.com/watch?v=VLc4ewu6lUI) 
- [Transactions in sql server and ACID Tests](https://www.youtube.com/watch?v=shkt9Z5Gz-U) 
   
##### Documentation
- [Transactions (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/transactions-transact-sql?view=sql-server-ver15)

### Stored Procedures

##### Videos
- [Stored procedures in sql server](https://www.youtube.com/watch?v=Qu3E-oncF3g) 
- [Stored procedures with output parameters](https://www.youtube.com/watch?v=bldBshxuhMk) 
   
##### Documentation
- [Stored Procedures (Database Engine)](https://docs.microsoft.com/en-us/sql/relational-databases/stored-procedures/stored-procedures-database-engine?view=sql-server-ver15)

### JOINs

##### Articles
- [SQL Joins](https://www.w3schools.com/sql/sql_join.asp)

### Normalization

##### Articles
- [Database normalization](https://www.w3schools.in/dbms/database-normalization/) 

### SQL databases

##### Articles
- [SQL Databases comparison](https://db-engines.com/en/system/Microsoft+SQL+Server%3BMySQL%3BPostgreSQL) 

### ACID

##### Articles
- [What does ACID mean in Database Systems?](https://database.guide/what-is-acid-in-databases/) 

---

## NoSQL

##### Videos
- [An Introduction To NoSQL Databases](https://www.youtube.com/watch?v=uD3p_rZPBUQ)

### Difference from SQL

##### Articles
- [SQL vs NoSQL: What's the difference?](https://www.guru99.com/sql-vs-nosql.html) 

### Types of NoSQL databases

##### Articles
- [Learn NoSQL Features, Types, What is, Advantages](https://www.guru99.com/nosql-tutorial.html)
- [A Comparison of NoSQL Database Management Systems and Models](https://www.digitalocean.com/community/tutorials/a-comparison-of-nosql-database-management-systems-and-models)

### SQL vs NoSQL

##### Videos
- [SQL vs NoSQL or MySQL vs MongoDB](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y) 
- [SQL vs NoSQL: проблема выбора](https://www.youtube.com/watch?v=zOEvutrfYt0) 
   
##### Articles
- [When to use SQL vs NoSQL](https://www.integrant.com/when-to-use-sql-vs-nosql/)

### NoSQL databases

##### Articles
- [Best NoSQL databases](https://www.improgrammer.net/most-popular-nosql-database/)

### CAP theorem

##### Videos
- [Cap Theorem](https://www.youtube.com/watch?v=7XXwbul6GxA)

##### Articles
- [CAP Theorem and Distributed Database Management Systems](https://towardsdatascience.com/cap-theorem-and-distributed-database-management-systems-5c2be977950e) 
- [An Illustrated Proof of the CAP Theorem](https://mwhittaker.github.io/blog/an_illustrated_proof_of_the_cap_theorem/) 

---

## File Storage

### Amazon S3

##### Videos
- [AWS S3 - Bucket, Objects, Versioning, Bucket Policy, LifeCycle, Storage Classes](https://www.youtube.com/watch?v=mt32JEAxrA4)

##### Documentation
- [What is Amazon S3?](https://docs.aws.amazon.com/AmazonS3/latest/dev/Welcome.html) 

### Azure Storage

##### Videos
- [Azure Blob Storage Tutorial - Setup & Explore with Azure Portal](https://www.youtube.com/watch?v=-sCKnOm8G_g)

##### Documentation
- [Introduction to Azure Blob storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction)
- [Quickstart: Azure Blob storage client library v12 for .NET](https://docs.microsoft.com/en-gb/azure/storage/blobs/storage-quickstart-blobs-dotnet)

### File System

##### Videos
- [File I/O](https://www.youtube.com/watch?v=HKqMqFJr4SY) 
   
##### Articles
- [Working with Files](https://www.codeproject.com/Articles/819158/Working-with-Files-Using-Csharp-and-NET-Framework)

### Best practices

While deciding where and how to store your files you should address and consider few things and possibilities:

1. Local File System

	1.1 Do your files need to be accessible from N server instances, i.e. you have distributed system? If that's the case, Local File System storage is not an option.

	1.2 Does the Read/Write speed of your hard drive suits your performance needs? You should think about drives which are best suited for file storage.

2. Database

	2.1. What's the average size of files you working on? There are different options to store files inside MS SQL database.

	2.2. How strong is your database server? If you are having distributed environment, you should keep in mind that database load will be higher due to additional file storage management and handling.

3. Cloud Storage (Amazon s3, Azure File storage, etc...)

	3.1. How good is server's network bandwidth? You should be aware that the server will fetch file via network

	3.2. Do you find the storage expenses suitable? There are different options, you should research what's the best for your use-case

Last but not least, meta data and storage reference should be stored inside database. You can even achieve (with good table architecture) possibility to have different files stored on a different locations (i.e. multiple servers) in a different way (e.g. LFS, Cloud)

### NFS

##### Documentation
- [Network File System overview](https://docs.microsoft.com/en-us/windows-server/storage/nfs/nfs-overview)
- [NTFS overview](https://docs.microsoft.com/en-us/windows-server/storage/file-server/ntfs-overview)

---

## Caching

### Redis

##### Articles
- [How To Use Azure Redis Cache In C#](https://www.c-sharpcorner.com/article/how-to-use-azure-redis-cache-in-c-sharp/)
- [Creating a Redis Service in ASP.NET Core 2.2 web API](https://medium.com/@matthew.bajorek/creating-a-redis-service-in-asp-net-core-2-2-web-api-17b8b5704454)

##### Documentation
- [Documentation](https://redis.io/documentation)
- [e-Book - Redis in Action](https://redislabs.com/ebook/foreword/)

### HTTP Cache

##### Articles
- [Response caching in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/performance/caching/response?view=aspnetcore-3.1)
- [Response Caching Middleware in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/performance/caching/middleware?view=aspnetcore-3.1)

### In-memory cache

##### Articles
- [Cache in-memory in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/performance/caching/memory?view=aspnetcore-3.1)

### Warm and cold cache

##### Articles
- [What is Cache Warming?](https://www.section.io/blog/what-is-cache-warming/)
---

## Session and cookies
##### Articles
- [Understanding ASP.NET View State](https://docs.microsoft.com/en-us/previous-versions/dotnet/articles/ms972976(v=msdn.10)?redirectedfrom=MSDN)
- [Introduction To ASP.NET Sessions](https://www.c-sharpcorner.com/UploadFile/225740/introduction-of-session-in-Asp-Net/)
- [Cookies in ASP.NET](https://www.c-sharpcorner.com/uploadfile/annathurai/cookies-in-Asp-Net/)
