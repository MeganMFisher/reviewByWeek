//Queries: 

// What triggers a query?

    //A query is triggered by the question mark. Everything after the ? goes on req.query. 


// What is req.query?

    //It is an object
    //The keys of the object come from the URL after the ?
    //The values of the object come after the equal sign after the key.
    
    // http://localhost:3000/api/favorites?key=value
    
    
    
// Complete the following by finishing the req.params and req.queries and stating what the value of each will be.

// http://localhost:3000/api/favorites?food=pizza?color=maroon?place=beach
    req.params
    req.query
    req.query
    req.query



//Middleware:

// What is middleware?

    //Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle
    
    //Middleware functions can perform the following tasks:

    // Execute any code.
    // Make changes to the request and the response objects.
    // End the request-response cycle.
    // Call the next middleware function in the stack. 
    // If the current middleware function does not end the request-response cycle, it must call next() to pass control to the next middleware function. Otherwise, the request will be left hanging.

//Why must you call next() in your middleware?

    //This is the trigger to indicate that our middleware was finished and to move on to the NEXT function in the chain. Remember you must call next in any middleware.

    //In order for the request to continue processing (other middleware or even our route handlers) you must call this argument; simply letting the function finish execution is not enough.
    
    // The reason next is exposed and must be explicitly called is for middleware, which performs I/O or async operations. Express.js has no way of knowing when your operation is complete before it can continue to the next middleware or route.
    

//Sessions

// What is a session?

  // A session is a place to store data that you want access to across requests. Each user that visits your website has a unique session.  You can use sessions to store and access user data as they browse your application.
  
  // Session handling in any web application is very important and must have thing, without it we won’t be able to track user and it’s activity.


//** Sessions can store their information in different ways. The popular ways to store session data is:

// In application memory
// In a cookie
// In a memory cache
// In a database


// Whats so important about the session secret?

    //The secret is used to encrypt the session ID, session data is stored server side always, the ID is how its matched up. It is also REQUIRED! 
 
 
//**resave: false, //When true it forces the session to be saved back to the session store, even if     the session was never modified during the request.

//**saveUninitialized: false //When true it forces a session that is "uninitialized" to be saved to    the store. A session is uninitialized when it is new but not modified.   


// What is a cookie?

    // A cookie is usually a small piece of data that gets sent between a web server to your web browser. It allows the server to store information relevant to a specific user. 
    
    
// How do cookies work?

    //The server issues a cookie that gets sent to the web browser and stored for a period of time (called the expiration time).
    // When a user makes a subsequent request to the web server, this cookie gets sent along with the request, and the server can read the information that is in it.
    // The server can manipulate the cookie if it needs to, and then sends it back to the browser.
    // Until the cookie expires, every time you make a request, your browser will send the cookies back to the server.
    

//**Issues with cookies: 

    //They can only store small bits of data, about 4KB usually.
    //They are sent in every request, and if you store a bunch of data in a cookie, it will increase the size of the requests, which will slow down your site’s performance.
    //If an attacker figures out how your cookies are encrypted (your secret key), then your cookies will be compromised. Attackers will then be able to read the data that is stored in the cookies, which can be sensitive user data.
    
    
    
// How do you access the session?

    //To store or access session data, simply use the request property req.session
    
    
// What are the four steps for how sessions works?

    //1. Browser sends the request to the Server with a cookie.
    //2. Server decrypts and looks at cookie data to get sessionId.
    //3. Server queries database with sessionId to get session information.
    //4. Server sends some response back with the cookie.

    

//Code Example:
    
    
let express = require('express');
let session = require('express-session');
let bodyParser = require('body-parser');

var app = express();

//MIDDLEWARE:

app.use(bodyParser.json());
app.use(session({
    secret: 'ldkajflkejfakjelkfj;lafke', //**Required** This is the secret used to sign the session ID cookie. The secret is used to encrypt the session ID, session data is stored server side always, the ID is how its matched up. 
    resave: false, //When true it forces the session to be saved back to the session store, even if the session was never modified during the request.
    saveUninitialized: false //When true it forces a session that is "uninitialized" to be saved to the store. A session is uninitialized when it is new but not modified.
}))
app.use( function(req, res, next) {
    const { session } = req;  // const session = req.session. To store or access session data, you simply use the request property req.session.
    console.log(session)
    if ( !session.user ) { //Checks if there is not already a session.user
        session.user = {  //If there isn't then create one and give it the key value pairs of 'username' with an empty string and 'favorites' with an empty array. 
            username: '', 
            favorites: []
        };
    } 
    next(); // <- This is the trigger to indicate that our middleware was finished and to move on to the NEXT function in the chain. Remember you must call next in any middleware.
    }
)

var port = 4000

//ENDPOINTS:

//Login 
app.get('/api/login', function (req, res) {
  req.session.user.username = req.query.email; //Takes the email from the query and assigns it to the session as the username.
  res.status(200).send(req.session.user) //Sends back the entire user object on the session.
});


//Get Favorites 
app.get( '/api/getFavorites', (req, res, next) => {
        const { user } = req.session; // const favorites = req.session.user.favorites
        res.status(200).send( user ) //Another way to send back the entire user object is to use object destructoring above and then just send your new user variable.
    })


//Add to Favorites
app.post( '/api/addFavorites', (req, res, next) => {
        const { favorites } = req.session.user; // const user = req.session.user
        let { fav } = req.query //const favorite = req.query.fav


        favorites.push(fav) //We are going to take what is on the query and push it to the favorites array on the user object on the sessions.
        res.send(req.session.user) //We will then send back the entire user object on sessions.

    })


//You can use this add favorites endpoint instead if you would like it to first check if the item is already in the favorites array and if it is not then it will add it to the array. Uncomment out the full endpoint to see the code and comments. 


// app.post( '/api/addFavorites', (req, res, next) => {
//         const { favorites } = req.session.user; // const user = req.session.user
//         let { fav } = req.query //const favorite = req.query.fav

        
//         const favIndex = favorites.findIndex( favItem => favItem == fav ); //We are using the .findIndex() method which will search through our favorites array on sessions to see if the fav item from our query is already in the array. If it is findIndex will return the index of the item if it is not findIndex will return -1.

//         if ( favIndex === -1 ) { //If we did receive -1 from findIndex() we now now the item is not already in the array and needs to be added. 
//                 favorites.push(fav) //We push the new item to the favorites array on the sessions.
//                return res.send(req.session.user) //We will then send back the entire user object on sessions.
//         }
//         res.status(200).send(req.session.user) //If we already have that item in the array we will just send back the entire user object on sessions.
// })


app.listen( port, () => { console.log(`Server listening on port ${port}.`); } );
    
    
    
    
    
    
    
    
