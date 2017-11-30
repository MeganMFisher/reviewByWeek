// What are the 3 ways to make requests?

    // 1. url requests: initial GET request made by website. Typically this will return an html page. www.google.com

    // 2. Resources Requests: html link, script, image sourse 

    // 3. AJAX(axios) Requests: These are the request your jS will make these can by any method. 



// What do you put into your terminal to create your npm package?

    //npm init. You can hit enter to hit all the defaults or add npm init -y which will add a flag to accept all the default settings. This allows us to install node modules into this project. 



// How do you run Node?

    //node server.js || node server/server.js alway point to server.js/index.js file to get it up and running.
    
  
    
// How do you install express and body-parser into your server?

    //npm install express body-parser
    
    
    
// How do you then use express in your server.js file?

      //You must make a variable to require/hold your express. Similar to import in react. 

     //const express = require('express');
     
     //const app = express() <==you must invoke express. It will help you handle api calls on your server. 
    
   
    
// Which ports are always available for your use?

    //Those about 3000. These are not reserved for specific use. 
    
    

// How do you set up your app.listen in your server.js?

    //app.listen(3000)  ||  app.listen(3000, () => {
    //  console.log('Listening on port ' + 3000)
    //}  //you can also set your port to a variable. App.listen tells your application to listen for all incoming requests. 
   


// What is an endpoint?

    //Function you can call on a remote server. 
    

// What are the parts of an endpoint? 

    //app.get('url', (request, response) => {
          // console.log('Ive been hit')
          // response.send('Endpoint Working!')
    // })
    
   // 1. Specifiy the method: app.get
   // 2. That method takes in the url and callback function as its parameters.
   // 3. The callback it takes the request and response as the parameters.
   // 4. Send a response back. 
   
   

// If we want to create something new what method do we use for our endpoint?

    //app.post(). When we make a post request we can send information in on the body of that request. req.body/request.body. 
    
    
    
// What does Postman allow us to do?

    //Test our endpoints without having to actually set up a front end.
    
    

// When sending a body with your endpoint in postman you must: 

    //Mark raw and json(application/json) and send your information as an object with key value pairs and double quotes on all strings. 
    
//**everthing must pass through the middleware before the function is invoked. app.use is how we use middleware.
  
// In order to send information on request.body you must use what piece of middleware?

    //body-parser. It will look at it and see if it has a body element and if it does it will parse it and make it available to your endpoints to be able to use and see the information on req.body. 
    
    //It will parse incoming request bodies in a middleware before your handlers, available under the req.body property.
  

// How do you set up your body-parser to be used?

    //const bodyParser = require('body-parser'); //can't use '-' because it will try and minus them so you must use camel case for the variable but body-parser does have to have the '-' after the require because that is the actual name of the middleward you are requiring.
    
    //app.use(bodyParser.json()); 

    
    
// What does nodemon do?

    //npm install -g nodemon. It is similar to live-server or the react hot loading and will watch for changes and restart your node when changes are made. It looks at your main property on your package.json so if that path is correct you don't have to tell nodemon which file to look for it will default to look at the main propery. You just run nodemon in your terminal to get it up and running.
    
    
    
// What are some common HTTP status codes?

    // 404: not found
    // 403: forbidden
    // 400: bad request - sent wrong type of information.
    // 401: not authorized
    


// Which REST methods to you have access to use the req.body? 

    // The body is only accessible on put, post, and delete. You do not have access to it on a get request. 
     
     

// How do you set up an endpoint with a parameter?

    //app.put('/api/books/:id', (req, res) => {
        // console.log(req.params.id) 
    // })
    
    //you give the parameter a name up in the url so in this endpoint it is called id and that is how you will access that parameter. You must have the : before the name you give the parameter. 
    
    //We use them on endpoints that require information for that endpoint to make since. Common use is an ID. 
    
    //Parameters that come in are ALWAYS a string and you must set up your code accordingly. 
    
    
// What does .find() do in Javascript? 

    //.find() is a Higher order function.

    //Will look through and return the first item that meets the condition you have set. 
    
    let bookToEdit = books.find(book => book.id === req.params.id * 1)
    Object.assign(bookToEdit, req.body)
    res.send(bookToEdit)
    
    var arr = ['betty', 'wilma', 'fred']

    var found = arr.find(e => e === 'betty')

    console.log(found)
    console.log(arr.splice(found, 1))
    console.log(arr)

    
    
//**adding '/api/' before each of the urls in your endpoints in your server.js will help keeps things clean and consistant throughout your app. It also helps to not tie up up front end urls with apis. Like if you have your url as /products but you use /products as your api rather than seeing the display of products they will see the ugly json object of product information. 


// Difference between put and patch?

    //With put you send back and entire copy of something. Will send you the whole modified thing back.
    
    //With patch you are not sending back the final product you are sending back instructions. 
    
    //Behaviorally they act the same way its just that symantic change. 
    
    
// What does express.static do?

    //Serves static files such as images, CSS files, and JavaScript files, use the express.static built-in middleware function in Express.

    //Pass the name of the directory that contains the static assets to the express.static middleware function to start serving the files directly. For example, use the following code to serve images, CSS files, and JavaScript files in a directory named public:
    
    // app.use( express.static( __dirname + '/../public/build' ) );
    
    //We just give it a path to the files we want to serve.
    
    //If your server and public are always siblings you can use the above file path without modification. 
    
    
//app.METHOD(URL, HANDLER)  Endpoint syntax. 