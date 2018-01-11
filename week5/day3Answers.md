




// What are the three primary types of authentication used on the internet?

    // -Have: Cookie, Cell phone (they text you the code), usb dongle
    // -Know: Passwords, Security questions
    // -Are: Fingerprints, eyeball scan



// Why is security growing?

    //Breaches and hacks are increasing. There are bad people on the internet. There are very bad people and there are a lot of them. There are people who want to drain your bank account, steal your grandma's social security, pretend to be you and misfile your taxes to get you in trouble, pretend to be you and sell drugs just to get people in trouble. 

    //As a developer you are responsible for helping protect your users from such attacks. 

    
    
    
// What is more secure the client or the server?

    //Can right click inspect and see all of the javascript files. Client side is not secure at all. 
    
    //Security should be server side. 
    
    
    
// How is basic auth set up?

    //Basic auth used to be http://username:password@somedomain.com/stuff




// How do you fix it so the basic auth doesn't leave you super open to security breaches?

    // To fix that we need to use https. S stands for secure. It encripts the data. It jarbles everything so only the server and client can see it and while it travels through the interweb it is jarbled and no one can see it. 
    
    
    
// Why would each request need username/password?

       // HTTP is stateless. It has no recollection of previous requests. 



// What is basic Authentication?

    // Very simple way to enforce access controls for web resources. Credentials are sent in the header of the request. Credentials are encoded. 


// What is encoding?

    // Encoding transforms data into another format using publicly available schemes and is easily resersible. All you need to decode is the algorithm used to encode. Encoding is not for keeping things secret. The goal is to safetly transport it.  


// What is encription?

    // Transforms data with the goal of keeping the info secret. 


// What is the best practice for storing passwords?

    // Hash and salt them. If you are hashing passwords, you should also salt. 


// What is hashing passwords?

    // Hashed passwords become 'random' string of characters. Not intended to ever be un-hashed. Server stores hashed password, not original. Same input, same algorithm, same hash. 


// What is passport?

    // Simple, unobtrusive authentication for Node.js

    // Authentication middleware for Node.js

    // Passport has many different strategies that we can use. Some of those include FB, Google, etc...



// Are HTTP requests stateless?

    // HTTP requests are stateless. The server doesn't remember. 


// What is auth0?

    // A passport strategy. 



// What do you need to install to use auth0? 

    // npm i passport passport-auth0 express-session express


// What order do you need to put passport.initialize, session, passport.session?

    // Session, passport.initialize, passport.session. It MUST be in that order in your code. 

    app.use(session({})); 
    app.use(passport.initialize());
    app.use(passport.session());



// What three pieces of information do you need to get from auth0.com?

    //Domain, Client ID, and Client Secret. 




// After setting session and passport and collecting those three pieces of information from auth0.com what do you do next to setup auth0?

    passport.user(new Auth0Strategy({
        domain: 'yourDomain',
        clientID: 'yourClientID',
        clientSecret: 'yourClientSecret',
        callbackURL: 'yourCallbackURL'   
    }))



// Why do you need a callbackURL?

    // Auth0 needs to know where to redirect your client back to after they have authenticated them.



// What will happen if you don't turn OIDC Conformant off on auth0.com?

    // It breaks all the things during developement. If your auth0 isn't working correctly and you don't know why check that first. 



// How do you add the require callback function to the invocation of passport.user?

    passport.user(new Auth0Strategy({
        domain: 'yourDomain',
        clientID: 'yourClientID',
        clientSecret: 'yourClientSecret',
        callbackURL: 'yourCallbackURL'   
    }, function(accessToken, refreshToken, extraParams, profile, done){

    }))



// Why do you need all 5 parameters and which ones will we use?

    //You have to pass in the first three to access the last two which are the ones we want: profile and done. 



// How do you create an endpoint that uses passport.authenticate to kick off authentication?


    app.get('/auth', passport.authenticate('auth0')); 
    // Login button hits this endpoint to start the process. Passport provides an authenticate() function, which is used as route middleware to authenticate requests. If this function gets called, authentication was successful. `req.user` contains the authenticated user.



// How do you setup the callback endpoint?

    app.get('/auth/callback', passport.authenticate('auth0', { 
    successRedirect: 'http://localhost:3000/#/private',
    failureRedirect: 'http://localhost:3000/#/'
    }))

    //Auth0 is going to hit this callback endpoint.

    // You need to tell it where to go if authentication is successful or if it failed. Be sure you sent them to your frontend not your backend port. 



// Can you combine these two endpoints into one?

    //Yes! 

    app.get('/auth', passport.authenticate('auth0', {
        successRedirect: 'http://localhost:3000/#/private',
        failureRedirect: 'http://localhost:3000/#/'
    }));



// What do you put inside the callback function of the invocation of passport.user?

    passport.user(new Auth0Strategy({
        domain: 'yourDomain',
        clientID: 'yourClientID',
        clientSecret: 'yourClientSecret',
        callbackURL: 'yourCallbackURL'   
    }, function(accessToken, refreshToken, extraParams, profile, done){
        done(null, profile)
    }))

    // Invoke done. The first argument is for errors if you aren't experiencing errors you can just put null there and the second is the profile that you want passed on. 




// How do you set up the serializeUser?

    passport.serializeUser(function(profile, done) {
    done(null, profile);
    });

    //Things you might do here : Serialize just the id, get other information to add to session



// How often is serializeUser invoked?

    //THIS IS INVOKED ONE TIME TO SET THINGS UP



// Where does serializeUser put the user?

    //PUTS 'USER' ON THE SESSION



// How do you set up the deserializeUser?

    passport.deserializeUser(function(profile, done) {
        done(null, profile); 
    });

    //Things you might do here : Query the database with the user id, get other information to put on req.user



// How often is deserializeUser invoked?

    //THIS IS INVOKED FOR EVERY ENDPOINT 



// Where does deserializeUser get the user?

    //The user comes from session where serializeUser put it. 



// Where does deserializeUser put the user?

    //PUTS 'USER' ON REQ.USER



// How do you setup your login button in your react?

    <a href='http://localhost:4000/auth'><button>Login</button></a>

    // Be sure you put it on whatever port your server is running on. 

    