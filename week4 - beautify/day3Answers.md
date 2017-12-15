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
    
    
    
    
//** Relationships: 
  // -one to many relationship
  // -parent to child relationship
    
    
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




// ##Black Diamond: 

// - Get all tracks on the playlist(s) called Music and show their name, genre name, album name, and artist name.
// At least 5 joins.

// **Solution**

// SELECT Playlist.Name, Genre.Name, Album.Title, Artist.Name
// FROM Playlist 
// JOIN PlaylistTrack ON Playlist.PlaylistId = PlayListTrack.PlaylistId
// JOIN Track ON Track.TrackId = PlaylistTrack.TrackId
// JOIN Genre on Genre.GenreId = Track.GenreId
// JOIN Album ON Album.AlbumId = Track.AlbumId
// JOIN Artist ON Artist.ArtistId = Album.ArtistId
// WHERE Playlist.Name = 'Music'




// ##eCommerce Simulation: 

// CREATE TABLE users (
//     id SERIAL PRIMARY KEY,
//     name TEXT,
//     email TEXT 
// )

// INSERT INTO users (name, email) VALUES ('Betty', 'Betty@gmail.com'),
// ('Wilma', 'Wilma@gmail.com'), ('Fred', 'Fred@gmail.com')


// CREATE TABLE products (
//     id SERIAL PRIMARY KEY, 
//     name TEXT, 
//     price INTEGER
// )

// INSERT INTO products (name, price) VALUES ('sweater', 12),
// ('socks', 5), ('pants', 20)


// CREATE TABLE orders (
//     id SERIAL PRIMARY KEY,
//     orderNum INTEGER,
//     productId INTEGER REFERENCES products (id)
// )

// INSERT INTO orders (orderNum, productId) VALUES (1, 1), (1, 2), (2,3), (2,1), (3, 3), (3, 2)




// ////Get all products for the first order:

// SELECT name, price, orders.orderNum, orders.productId
// FROM products
// JOIN orders ON orders.productId = products.id
// Where orders.orderNum = 1



// ////Get all orders:

// SELECT ordernum, productid, products.name, products.price
// FROM orders
// JOIN products ON orders.productId = products.id

// <!-- SELECT * FROM orders -->


// ////Get the total cost of an order ( sum the price of all products on an order ).

// SELECT sum(products.price)
// FROM orders
// JOIN products ON orders.productId = products.id
// WHERE ordernum = 1


// ////Add a foreign key reference from Orders to Users.

// ALTER TABLE orders
// ADD COLUMN userId INTEGER REFERENCES users (id)


// ////Update the Orders table to link a user to each order.

// UPDATE orders SET userId = 1 WHERE orderNum = 1;
// UPDATE orders SET userId = 2 WHERE orderNum = 3;
// UPDATE orders SET userId = 3 WHERE orderNum = 2;

// <!-- INSERT INTO orders (orderNum, productId, userId) VALUES (1, 1, 1), (1, 2, 2), (2, 3, 3), (2, 1, 2), (3, 3, 2), (3, 2, 3) --> 


// ////Get all orders for a user:

// SELECT *
// FROM orders
// JOIN users ON users.id = orders.userId
// WHERE users.Id = 1


// <!-- Select * from orders where userId = 1 -->

// ////Get how many orders each user has:

// SELECT count(orderNum)
// FROM orders
// JOIN users ON users.id = orders.userId
// WHERE users.Id = 2



// ##Black Diamond: 

// ////Get the total amount on all orders for each user:

// SELECT sum(price)
// FROM orders
// JOIN products ON products.id = orders.userId