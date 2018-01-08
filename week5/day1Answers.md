//// MEDIA QUERIES

// What are media queries?

    // It uses the @media rule to include a block of CSS properties only if a certain condition is true. The @media rule is used to define different style rules for different media types/devices.

    // Media queries are useful when you want to apply specific CSS styles that depend on the general type (such as print vs. screen), specific characteristics (such as the width of the browser viewport), or environment (such as ambient light conditions) of a device. As the number and variety of internet-connected devices continue to expand, media queries are becoming increasingly vital for building robust websites and apps.
    

// What's the difference between Extraction vs Enhancement in Joe's lecture?

    // Extraction is building an app for the desktop and optimize it for the tablet then mobile. You have to extract features and widdle it down to fit on a small device. The powerful rich features you got with the desktop is lost and mobile feels like an after thought. Desktop to Mobile

    // Enhancement is building for mobile first then building up to desktop. Deciding core features for mobile first. Building it first with mobile in mind. As you progress to tablet then desktop you add in features. 


    
// Why should you design mobile first when using media queries?

    //If you design for mobile before designing for desktop or any other device, it will make the page display faster on smaller devices. This is the trend not the rule. 
    

// Is order important?

    // Absolutely yes. It will read top to bottom and whatever is at the bottom will be used so if you change one element and the top then change it again at the bottom it will use the bottom change not the top. It is typical that your media queries are at the bottom of your file to make sure they are applied last. 


    
// How do you create a breakpoint?

    // We can add a breakpoint where certain parts of the design will behave differently on each side of the breakpoint.

    //@media(<set your condition in here>) {}

    //@media(min-width:750px) {
        //750px or greater
    //}
    


    
// What does Max-width condition below tell the media query?
@media (max-width: 600px)  {...}

    // Max-width: "If [device width] is less than or equal to 600px, then do {...}"




// What does min-width tell the media query?
@media (min-width: 600px)  {...}

    // Min-width: "If [device width] is greater than or equal to 600px, then do {...}"




    
// Can you combine max-width and min-width in one @media condition?

    // Yes. The query below will trigger only for screens that are 600-400px wide. This can be used to target specific devices with known widths.

    //@media only screen and (max-width: 600px) and (min-width: 400px)  {...}


//// CSS ANIMATIONS 

// What is so awesome about css animations?

    // They are super light. 


// What does @keyframes do?

    //It allows you to do animations based off certain times. When you specify CSS styles inside the @keyframes rule, the animation will gradually change from the current style to the new style at certain times. 


// Give an Example of doing an animation with keyframes: 

    // The animation code.
    @keyframes example {
        0%   {background-color: red;}
        25%  {background-color: yellow;}
        50%  {background-color: blue;}
        100% {background-color: green;}
    }

    // The element to apply the animation to. 
    div {
        width: 100px;
        height: 100px;
        background-color: red;
        animation-name: example;
        animation-duration: 4s;
    }


// What do the following transformation methods do?

    Translate(): Moves an element from its current position (according to the parameters given for the X-axis and the Y-axis).

    Rotate(): Rotates an element clockwise or counter-clockwise according to a given degree.

    Scale(): Increases or decreases the size of an element (according to the parameters given for the width and height).

    Skew(): Skews an element along the X and Y-axis by the given angles.




