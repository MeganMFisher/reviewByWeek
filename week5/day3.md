



// What are the three primary types of authentication used on the internet?



// Why is security growing?


    
    
// How is basic auth set up?




// How do you fix it so the basic auth doesn't leave you super open to security breaches?

    
    
    
// Why would each request need username/password?



// What is basic Authentication?



// What is encoding?



// What is encription?



// What is the best practice for storing passwords?



// What is hashing passwords?



// What is passport?



// Are HTTP requests stateless?



// What is auth0?



// What do you need to install to use auth0? 



// What order do you need to put passport.initialize, session, passport.session?



// What three pieces of information do you need to get from auth0.com?



// After setting session and passport and collecting those three pieces of information from auth0.com what do you do next to setup auth0?



// Why do you need a callbackURL?



// What will happen if you don't turn OIDC Conformant off on auth0.com?

    passport.user(new Auth0Strategy({
        domain: 'yourDomain',
        clientID: 'yourClientID',
        clientSecret: 'yourClientSecret',
        callbackURL: 'yourCallbackURL'   
    }))




// How do you add the require callback function to the invocation of passport.user?



// Why do you need all 5 parameters and which ones will we use?



// How do you create an endpoint that uses passport.authenticate to kick off authentication?



// How do you setup the callback endpoint?



// Can you combine these two endpoints into one?



// What do you put inside the callback function of the invocation of passport.user?

    passport.user(new Auth0Strategy({
        domain: 'yourDomain',
        clientID: 'yourClientID',
        clientSecret: 'yourClientSecret',
        callbackURL: 'yourCallbackURL'   
    }, function(accessToken, refreshToken, extraParams, profile, done){

    }))



// How do you set up the serializeUser?



// How often is serializeUser invoked?



// Where does serializeUser put the user?



// How do you set up the deserializeUser?



// How often is deserializeUser invoked?



// Where does deserializeUser get the user?



// Where does deserializeUser put the user?



// How do you setup your login button in your react?


