# DapperASPNetCore
 This repo contains the source code for the "Implementing Dapper in ASP.NET Core Web API." 
# What is Dapper 
 Dapper is a simple object mapper, or a micro-ORM, for .NET that extends the IDbConnection interface. It provides a set of extension methods for querying and executing commands against a database in a performant manner. Unlike some ORMs, Dapper doesn't attempt to translate your .NET queries into SQL. Instead, you write SQL statements directly, just as you would with SQL Server. This direct approach not only boosts performance but also ensures SQL injection safety when used with parameterized queries – a best practice that Dapper encourages.
 
 - Dapper supports synchronous and asynchronous method executions. We’ll use the asynchronous version of those methods.
 # About Extension Methods
  Dapper extends the IDbConnection interface with these multiple methods:

- Execute – an extension method that we use to execute a command one or multiple times and return the number of affected rows
- Query – with this extension method, we can execute a query and map the result
- QueryFirst –  it executes a query and maps the first result
- QueryFirstOrDefault – we use this method to execute a query and map the first result or a default value if the sequence contains no elements
- QuerySingle – an extension method that executes a query and maps the result.  It throws an exception if there is not exactly one element in the sequence
- QuerySingleOrDefault – executes a query and maps the result or a default value if the sequence is empty. It throws an exception if there is more than one element in the sequence.
-  QueryMultiple – an extension method that executes multiple queries within the same command and maps results
  
Dapper provides an async version for all these methods (ExecuteAsync, QueryAsync, QueryFirstAsync, QueryFirstOrDefaultAsync, QuerySingleAsync, QuerySingleOrDefaultAsync, QueryMultipleAsync).

we can install two required packages :-
- Dapper – PM> Install-Package Dapper
- SQL Client – PM> Install-Package Microsoft.Data.SqlClient

When to Choose Dapper or Entity Framework
# Choose Dapper When
- Performance is a top priority, especially for read-heavy applications.
- You need direct control over the SQL queries.
- You’re dealing with a legacy database or complex SQL queries.
- You prefer working with a lightweight tool and are comfortable handling some of the database complexities manually.
# Choose Entity Framework When
- You need a full ORM with features like change tracking and lazy loading.
- You prefer using LINQ for querying.
- You’re working on a data-centric application where the database schema is closely tied to the domain model.
- You want to take advantage of features like migrations for database schema management.

Performance & Lightweight are the major benefits we get with Dapper.

 
