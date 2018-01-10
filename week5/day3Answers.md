




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



// What three pieces of information do you need to get from auth0.com?

    //Domain, Client ID, and Client Secret. 



