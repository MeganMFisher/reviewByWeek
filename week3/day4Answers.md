// What two places to you need to use your database connection string?

    //SQL Tabs to run your sql statements 
    
    //Server.js file within the invocation of massive to connect your project to your database. 
    
    
    
// What do you have to add at the end of your connection string?

    //?ssl=true : Heroku requires this.



// What is Massive.js?

    //MassiveJS is a dedicated PostgreSQL data access tool that embraces SQL instead of completely abstracting it.
    
    // It is a node module that is designed specifically to connecting to PostgreSQL. You can execute sql queries and get the result back.
    

// How does massive work?

    //massive-js works by converting your SQL queries, held in files, into JS functions.

    
    
// How do you bring in massive in your application?

    //npm install massive
    //const massive = require('massive');
    
    

// How do you use massive in your application?

    //massive('postgres://postgres:@localhost/class-demo').then(db => {
          //console.log(db) 
    // })

    // Massive is a function that takes in the connection string and will give back a promise after the db connection is made. If you console log the response in the promise you will get the db tables. 
    
    
    
// What does app.set('db', db) do?

      //It stores the db on the app object as a key value pair. 
    
    
  
// Why is it a good idea to put your app.listen within the promise of your massive invocation?

    //We are able to ensure our db connection is setup first before it starts listening so we don't have any endpoints hit before the db has connected.
    
    
    
// What is the syntax for putting your app.listen within the promise of your massive invocation?

    massive(config.connectionString).then(db => {
      app.set('db', db);
      app.listen(port, () => {
        console.log('Started server on port', port);
      });
    });
  
  

// What folder to you put your sql files?

      //db


// How do you access the db from your express app in your endpoint?

      // const db = req.app.get('db') Lets us access the db in our endpoints. 
      
      // the 'db' in the req.app.get has to be the same as the name of the database in the app.set('db', db)
 
 
// How do you use the sql file in your db folder?

      // using dot notation on the db and invoking the name of the file. 
      // const db = req.app.get('db')
      // db.getAllInjuries()
 
     
      
// Give an example of an endpoint that uses as sql file from the db folder.

      app.get('/', (req, res) => {
        const db = req.app.get('db')
        db.getAllInjuries().then(injuries => {
          res.send(injuries);
        })
      
      });
      
      
// How do you take an argument into sql?

    // $1 
    
    
// How do you pass in arguments into the invocation of the sql file?

    //db.getAllInjuries([req.query.state]) 
    
    //If there is just one argument you don't need the array if there is more than one you have to put them all into an array.
    
    

// If you do = $1 in the sql file it is case sensitive? True or false.

    //True.
    
    //**ilike is case incensitive like. 

    //**upper($1) if you want it to come in always as an uppercase string. 


// If you add returning * at the end of your sql file what will it do?

    //Its a way of saying select these columns that I want on the thing that just got created. Your response from your promise will be whatever happened in your sql query.
    
    
// What is the difference between PUT vs PATCH?

  //put: replace all of it.
  //patch: update or append to it


// How would you set up a seed file in your db folder?

    //DROP TABLE IF EXISTS users; 
    
    // CREATE TABLE IF NOT EXISTS users (
    //     id SERIAL PRIMARY KEY,
    //     name TEXT,
    //     age INTEGER,
    //     country VARCHAR(80)
    // )
    
    // INSERT INTO users (name, age, country)
    // VALUES 
    // ('Betty', 25, 'England'),
    // ('Wilma', 34, 'Ireland'),
    // ('Fred', 32, 'Iceland'),
    // ('Bamm-Bamm', 2, 'England'),
    // ('Pebbles', 3, 'Ireland');




