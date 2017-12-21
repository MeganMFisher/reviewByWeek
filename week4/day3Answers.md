// ## Alter table:

// What does alter table do?

    //It changes the schema of the table.
    


// ### Adding columns: 
    
// What is the basic syntax for adding a column to a table?

    //ALTER TABLE <table name>
    //ADD COLUMN <column name> <data type>
    
    
    
// How do you add a column with a foreign key?

    // ALTER TABLE <table name>
    // ADD COLUMN <data type> REFERENCES <other table name>  [(<primary key column>)]

    //You have to add the column first or it will not allow you to add a foreign key when altering a table.  
    
    // It will automatically reference the primary key of that table so that part is optional.
    


// ## Alter column data types:    
    
// How do you change a data type of a specific column?

    // ALTER TABLE <table name>
    // ALTER COLUMN <column name>
    // SET DATA TYPE <data type>
    
    //OR 
    
    // ALTER TABLE <table name>
    // ALTER <column name>
    // SET DATA TYPE <data type
    
    //OR 
    
    // ALTER TABLE <table name>
    // ALTER <column name>
    // TYPE <data type
  
  
    
// When will postgreSQL allow you to change the data type?

    //Only when it makes sense with the data that is already in the column. If you have a bunch of text in the column you can't changed the data type to be an integer that won't work. 
    
  
  
// ## Renaming Columns  
    
// How do you rename a column?

    // ALTER TABLE <table name>
    // RENAME COLUMN <column name>
    // TO <new column name>
    


// ## Dropping a table:    
    
// When are you not allowed to drop a table?

    //If you drop a table everything is gone. If you have a foreign key constraint it will not allow you to drop it. If its connected to any other table it will not allow you until you remove the restraint then you can drop the table. 
    
    
    
// What is the syntax for dropping a table?

    //DROP TABLE [IF EXISTS] <table name>
    
    // [IF EXISTS]  is optional. If you have it it won't throw errors if it doesn't exist. 
    
    //You can do this on create and drop tables.  IF EXISTS or IF NOT EXISTS.
    
    
    
// What is a foreign key?

    //FOREIGN KEY: It is a key not from this table it is a key from another table therefore it is foreign and will reference another table. Often the primary key of the other table will be the reference to the second table as the foreign key. This takes planning and thinking ahead in your application. How you plan your database tables and their relationships between each other.
    
    //It needs to always reference something that is totally unique otherwise it doesn't work.
    
    
    
// How do you create a table with a foreign key?

    //CREATE TABLE <table name>
    // <column name> <data type> <constrants>
    // <foreign key column name> <data type> REFERENCES <other table name>  [(<primary key column>)]

    //It will automatically reference the primary key of that other table so the last part is optional


    
// What does a join do?

    //Thus far, our queries have only accessed one table at a time. Queries can access multiple tables at once, or access the same table in such a way that multiple rows of the table are being processed at the same time. A query that accesses multiple rows of the same or different tables at one time is called a join query.

    //A join is where you can make a query between two tables. You join the two tables together using the primary and foreign key as your connection. It will give you a new table with the new data. 
    
    

// What is the basic syntax for writting a join?


      // SELECT <columns that we want to select> 
      // FROM <table 1>
      // JOIN <table 2> ON <table 1>.<primary key> = <table 2>.<foreign key>

    
      // SELECT <first table name>.<column name>, <second table name>.<column name>
      // FROM <first table name>
      // JOIN <second table name> ON <first table Name>.<primary key> = <second table name>.<foreign key>
      // WHERE <column name> = <constraint>



// How do you make an alias in your query?

    //SELECT al.Title
    // FROM Album [as] al 
    
    //You can remove the as and just put the alias second. It will only work for this specific query. Unlike JS you can tell the query what the alias is after you've already used the alias in that query.
    
    
    
// How do you write nested queries?

    // SELECT <columns that we want to select>
    // FROM <table 1>
    // WHERE <primary key or something else> IN 
    //     ( 
    //     SELECT <column name>
    //     FROM <table 2>
    //     WHERE <foreign key or something else> = <contraint>
    //     )
    
    
    // SELECT <columns that we want to select>
    // FROM <table 1>
    // WHERE <query to match> IN 
    //     ( 
    //     <new select statement with table 2 matches query to match
    //     )

    //Most of the time default to the join rather than nested queries. You can nest them as many layers deep as you would like. Sometimes working from the inside out with nested queries is the easiest. 



// What is an aggregate function in SQL?

    //count(), sum(), etc



// What does group by does?

    //Takes your column and groups any similiar information.
    
    // - with select statements --- any ungrouped column needs to be with an aggregate function. 

    // -will group any values that are the same from the grouped column.
    
    

// What is the syntax for group by?

    // SELECT <grouped column name>, <any column ungrouped needs to be with an aggregate function>
    // FROM <table name>
    // GROUP BY <column name being grouped>
    
    
  
// Where does the where clause go when being used with a group by?

    // Before the Group by. 

    // SELECT <grouped column name>, <any column ungrouped needs to be with an aggregate function>
    // FROM <table name>
    // WHERE <column name> = <constraint>   
    // GROUP BY <column name being grouped>
    
    // If you use a where clause you have to do it before the group by because that is when it happens. 



// Where does the having clause go when being used with a group by?

    // After the Group by. 

    // SELECT <grouped column name>, <any column ungrouped needs to be with an aggregate function>
    // FROM <table name>
    // GROUP BY <column name being grouped>
    // HAVING <aggregate function> 
    
    // Most of the time when using having you will be using an aggregate function. You will ONLY be using the having clause with group by. 
    
    

// How do you drop a column?  

      // ALTER TABLE <table name>
      // DROP COLUMN <column name>


// How do you rename a column?

      // ALTER TABLE <table name>
      // RENAME TO <new column name>




// What does the Not null constraint do when creating a db table? 

    // A not-null constraint simply specifies that a column must not assume the null value



// How does the unique constraint work?

    //Unique constraints ensure that the data contained in a column, or a group of columns, is unique among all the rows in the table.

    // Unique doesn't matter when it comes to null. 




// Example of when a unique constraint is important?

    // Login usernames.
    // FB Login auth id
    // email sometimes

    // Any time you want to make sure there is not more than one in your db that is when unique comes in. 




// What is the check constraint?

    // A check constraint is the most generic constraint type. It allows you to specify that the value in a certain column must satisfy a Boolean (truth-value) expression.

    For instance, to require positive product prices, you could use:

    CREATE TABLE products (
        product_no integer,
        name text,
        price numeric CHECK (price > 0)
    );



// What type of relationships are there?
    // -one to many relationship
    // -one to one
    // -many to many



// What is an example of a many to one type of relationship?

    // An author with many books they have written. 

    // A user with many products in the cart.

    // Likened to a parent-child relationship. One author(parent) many books(children)



// What is an example of a many to many type of relationship?

    // Multiple authors taking multiple flights to book signings. 









