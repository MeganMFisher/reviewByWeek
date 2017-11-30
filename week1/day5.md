// What do react components contain?


// What does DOM stand for and what is it?


// What is the main reason for the DOM?


//**If the UI is what the people see performing on the stage the DOM is the tech team behind the curtains preparing everything to display next. React takes the concept of the DOM and copies it to also have the shadow DOM. The DOM is the staging area and the virtual/shadow DOM is the staging area for the staging area. React maintains and runs the virtual DOM and pushes to the DOM.



// How do you use create react app?


// What is the number one rule for the name of your components? 


// How do you import react into your component?


// What is import doing?


// What is the default file extension on imports?


// When importing files into your component how do you start your file path if it is one of your files or if it is installed externally? 



// How many defaults do you have per file?


//Most React component files follow what structure?



//**Every component must have a render function. Without it react won't know what to put on the screen. That render function returns html/JSX and that is what react puts on the screen. 

//**Any JS file you can export. If you do export however, it MUST be named. 

//**It is good practice to name files and components the exact same name so your code is more organized. 


// What are some of the differences between html and JSX?



// Where do you define state?



// How do you inject a component into another component?



// What does this.setState = {} tell React?



// React is Unidirectional what does that mean?



// What two types of data do we use in a React app?



// Does each component have to use state?



// In React what are props?



// Where is the correct place to set the initial state of a component?



// What is one major reason why React is much faster than other libraries and frameworks?



//**VOCAB : class method = A class method is a method on a class. It is a sibling to the constructor function.

//**VOCAB: Run-time means the state of the code while the application is running, not while we're writing it.


//**What does React do?

  //React's primary purpose is to help you render to the DOM. React makes it easy to put elements on the DOM, respond to user interaction, and change elements on the DOM only when they need to change. 

//**How does React do that?

//**React has a tool called JSX - using JSX, you will write elements directly in your Javascript similar to how you write HTML. Using JSX, we could write something like: var div = <div></div>, something we never could have done in plain Javascript. With JSX, we can code the elements and the rules about how and when to render them, before they ever enter the DOM.

//**Component-based development

//**React excels at creating small components, or pieces, that fit together to make something bigger. Building with components makes it easier to test and find problems, easier to work with a group on the same project, and easier to make changes later. 

//**"Your components tell React what you want to render – then React will efficiently update and render just the right components when your data changes." 1 In React, a page could be a component built of many smaller components which each handle different tasks. This way, anytime we need to change anything, we know exactly where to make the change, and the change will happen everywhere we use that component. 

//**The virtual DOM

//**The DOM, or Document Object Model, is the structure of objects created by HTML. React stands between you and the DOM to make rendering simpler and to make performance better. React does this by working with a virtual DOM. 

//**"Think of the virtual DOM as React's local and simplified copy of the HTML DOM. It allows React to do its computations within this abstract world and skip the 'real' DOM operations, often slow and browser-specific.

//**"There's no big difference between the 'regular' DOM and the virtual DOM. This is why the JSX parts of the React code can look almost like pure HTML." 2







