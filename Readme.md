# __SQL# Projects Portfolio__

This is a collection of the SQL projects that I have as part of my portfolio thus far, again these vary from smaller code snippets to larger programs. They where developed in Microsoft SQL Server Managament Studio.  

&nbsp;

## __Library Management System Project__ [(CODE)](https://github.com/ProfSFrink/sql_portfolio/blob/master/Library%20Management%20System%20Project.sql)

---

### __IMPLEMENTS: Relational Databases, Inner & Outer Joins, Conditional Statments, Try / Catch Code Blocks, Stored Procedures, Parameters__

A SQL script that creates a relational database to manage a library and track the loaning of books. The dB has seven tables to represent the library branches, books, book authors, book publishers, borrowers, the number of copies of a book, and then finally a table to track the books that are loaned out, [(SCHEMA)](https://github.com/ProfSFrink/sql_portfolio/blob/master/Library_Project_Schema.png). The books themselves are tracked through a BookID which creates a relationalship between the books table, the authors table, this is a one-to-many relationship as a book can only have one author but an author can have many books, then the publisher table links to the books table thanks to the publisher name.

The books copies table relates to the books table through BookID and the Library Branch table through BranchID, this allows us to see how many copies of a book a particular library branch has on hand. Then we have a borrower table for the people renting the books themselves. The main table that ties everything together in the system is the book loans table this has a relationship with the borrowers table and the books table, so we can see which borrowers have checked which book out and when it is due back. See the linked database schema for a visual diagram of these relationships.

The database has a number SQL queries, three of which are written as stored procedures and support parameters, and with error checking, which is implemented through use of try / catch blocks and conditional statements. Firstly there are two simple queries to show that all of the relationships between the tables in question are working as intended, one to show all books in the system with their respective authors and publishers this is done through use of an outer join. Then a second one to show all the data that exists in the system, so all borrowers, books, library branches and borrowers, this is done using an inner join. 

Then movving on to the stored procedures the first allows us to see how many copies of a book a particular library branch has on hand to loan out and if the book doesn't exist in the system an appropriate error message is generated, if the book does exist then the apporiate data is returned to the user, the name of the branch and book are passed in to the procedure as parameters, this procedure utilises a full outer join. This is then iterated upon in the second procedure which allows you to see how many copies of a book are available to loan out by every library branch, again error checking is implemented and the name of the book is passed in via a parameter, and again uses a full outer join. Then the final procedure shows the user the names of all borrowers who do not currently have any books checked out by the system, this is done by exploting the relationship between the borrowers and book loans table, and any borrower card number that do not feature in the books loans table, this makes use of a where not conditional statement.

There is also a seperate SQL file containing test queries that I wrote during the project to test things as the system was developed. [(CODE)](https://github.com/ProfSFrink/sql_portfolio/blob/master/Library%20Management%20System%20Project%20-%20TESTING%20QUERIES.sql)
