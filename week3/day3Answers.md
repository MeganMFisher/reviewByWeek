// What dialect of SQL do we use?

  //postgreSQL : Relational database management system. 
  //SQL is used to communicate with a database.


// What is a relational database?

    // A database structured to recognize relations among stored items of information.

    //A relational database (RDB) is a collective set of multiple data sets organized by tables, records and columns. RDBs establish a well-defined relationship between database tables. Tables communicate and share information, which facilitates data searchability, organization and reporting.

    //RDBs use Structured Query Language (SQL), which is a standard user application that provides an easy programming interface for database interaction.

    //RDB is derived from the mathematical function concept of mapping data sets and was developed by Edgar F. Codd.




// What is SQL very picky about?

    //Semi-colons and trailing commas. It will break all the things. Syntax is extremely important to SQL. 
    
    
    
// How does SQL interpret single and double quotes?

    //Double quotes interprets it as a column name. Single quotes as a string. 

    
    
// How do you have add a quote in a string into your query?

    //'I''m excited for postgreSQL.' -two single quotes for a quote in a string. 
    
    
    
// What is the syntax for creating a table in postgreSQL?

    // CREATE TABLE [tableName] (
    //   [column name] [data type] [contraints - optional],
    //   [column name] [data type] [contraints - optional]
    // );
    
    

// How do you create an autoincrementing id in your database?

    //id SERIAL PRIMARY KEY : Database will take care of creating a new id for you with each insertion into the database. Best way to put in your autoincrementing id for each table. 
    
    

// Create a products table with an id, name, and price?

    // CREATE TABLE product (
    //   id SERIAL PRIMARY KEY,    
    //   name TEXT, 
    //   price FLOAT 
    // )
    
    
    
// What do each of these datatypes do?

    // Numeric Types  
    //     - FLOAT : up to 15 numbers after decimal point.
    //     - INTEGER : No decimal places. It will round it for you so your numbers won't be super precise. 
    //     - DECIMAL : hundreds of numbers after decimal point so if you need super specific numbers


    // Character Types 
    //     - TEXT : Character length is unlimited.
    //     -VARCHAR(n) : n represents a number. VarChar = varying character. Character length is   limited based off number. 



// What is an SQL Statement?

    //Also known as query. Ends with a semi-colon.
    
    
// What does * mean?

    //All the things. Everything. 
    
    
    
// What is the syntax for a select statement?

    //SELECT *
    //FROM [column-name]
    
    // SELECT LastName, FirstName  
    // FROM Customer   
    
    //You can switch the column names however you'd like and they data will come back in the way you ordered the columns in your select statement. 
    
    
    
// What does the DISTINCT clause do?

    // It removes duplicates. 
    
    // The DISTINCT clause is used in the SELECT statement to remove duplicate rows from the result set. 
    
    // SELECT DISTINCT column_1
    //   FROM table_name;
    

// What does WHERE do and give an example of how to use it? 

    // It makes it conditional so you can be more specific about what you are selecting.
    
    // If the WHERE clause is specified, all rows that do not satisfy the condition are eliminated from the output.
    
    //SELECT *
    //FROM Invoice
    //WHERE Total > 5

    
    
// Can you use conditional operators in your queries? 

    // You can use conditional operators in your queries. > < >= <= != = etc. 
    // You can use =. It isn't like JS it doesn't assign it the value it just tests if they are equal. 
    
    
    
// How do you check for null values?

    //You CAN'T do != Null;
    //You MUST use IS NOT NULL; or IS NULL;
    
    
    
// If you want to test that two conditions are met what would you use?
    
    //AND

    // SELECT * 
    // FROM orders
    // WHERE billingState IS NOT NULL AND billingPostalCode IS NOT NULL;
    
   
    
// If you want to test that one of two conditions are met what would you use?

    // OR 
    
    // SELECT * 
    // FROM orders
    // WHERE total = $50 OR billingPostalCode IS NOT NULL;
    
    
    
// Give an example of using BETWEEN and NOT BETWEEN?

    // BETWEEN: 
    
    // NOT BETWEEN: 


    // SELECT *
    // FROM Invoice
    // WHERE Total BETWEEN 1.98 AND 5. 

    // SELECT *
    // FROM Invoice
    // WHERE Total NOT BETWEEN 1.98 AND 5. 



// When would you use IN and NOT IN and give examples?

    // Useful if you have more than one value in a single column you are looking at so you don't have to make multiple queries. 
    
    // You use the IN operator in the WHERE clause to check if a value matches any value in a list of values. 
    
    // SELECT *
    // FROM Invoice
    // WHERE BillingCountry IN('USA', 'Germany')
    
    // SELECT *
    // FROM Invoice
    // WHERE BillingCountry NOT IN('USA', 'Germany')


// What does the LIKE clause do?  

    // It matches partials. The PostgreSQL LIKE operator is used to match text values against a pattern using wildcards. 
    
    
// What will each of the following LIKE clauses return?

      // WHERE name LIKE 'A&'  //Returns names starting with A
      // WHERE name LIKE '%A'  //Returns names ending with A
      // WHERE name LIKE '%A%' //Returns names with a A anywhere in it


// How would you check the employees table in your database to give you all the employees with the firstName that ends with N?

    //SELECT *
    //FROM employees
    //WHERE firstName LIKE '%N'


// What is the default for ORDER BY?

      //Ascending. However it is best to put ASC or DESC after the column name so it is easier to read and is more clear about what you are getting back. 
      
      
// Write an example of using ORDER BY where the items are descending?

      //SELECT *
      //FROM invoices
      //ORDER BY total DESC 
      
      
// How do you limit the number of rows you get returned when using ORDER BY?

      //SELECT *
      //FROM invoices
      //ORDER BY total DESC 
      //LIMIT 10



// What does each of the following functions do?

      //count(*)  :  Returns a number with the count of how many rows there are.
      //avg()     :  Returns the average of the numbers in that column.
      //sum()     :  Returns the sum of the numbers in that column.
      //min()     :  Returns the smallest number in that column.
      //max()     :  Returns the largest number in that column. 
      
      

// How do you give a select statement an alias?

    //SELECT max(Total) as HighestNumber, count(*) as Total
    //FROM invoice
    //WHERE BillingCountry = 'Germany'
    
    //Aliases can make your data easier to read. 
    
    
    
// Write an example of inserting data into a database?

    //INSERT INTO [table name] ([column-name], [...column-name])
    //VALUES ([value], [...value])
    
    //Order is very important here! 
    
    // INSERT INTO employees (firstName, lastName)
    // VALUES ('Wilma', 'Flintstone')
    
    
    
// What does RETURNING * do?

    //You can use this after you make a query to return the response.
    
      //INSERT INTO inventory (name, shelf, bin, image, price)
      // VALUES ('A1', 'A', 1, '/imagePath', 2.34)
      // RETURNING *;
    
    
    
// Write an example of updating data in a database?

    // UPDATE employees
    // SET firstname = 'Fred'
    // WHERE lastName = 'Flintstone'
    
    //You need to put a where clause so it doesn't change all of the firstnames in your entire database. Id is usually the best where clause for updates to absolutely make sure you have selected the correct row. 
    
    
// Write an example of deleting a row in a database?

    //DELETE FROM employees
    //WHERE employeeID = 10
    
    //You need to put a where clause so it doesn't delete your employees table in your database. Id is usually the best where clause for deletes as well to absolutely make sure you have selected the correct row. 
    
    //Will delete your row but won't shuffle ids around to fill that whole. 
    
    


// git stash 
// git checkout -b newBranch
// git stash pop 