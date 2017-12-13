// What do react components contain?

    // Each component will have UI, Logic, and Data. UI is referring to html, css, js anything that affects the visual aspect of the applicaation. 


// What does DOM stand for and what is it?

    // Document object model. It is the staging area for the rest of your code. A model or representation of what needs to be displayed on the screen. The DOM acts as the staging area for the render.  


// What is the main reason for the DOM?

    //The main reason for having the DOM is preformance.
    
    
//**If the UI is what the people see performing on the stage the DOM is the tech team behind the curtains preparing everything to display next. React takes the concept of the DOM and copies it to also have the shadow DOM. The DOM is the staging area and the virtual/shadow DOM is the staging area for the staging area. React maintains and runs the virtual DOM and pushes to the DOM.


// How do you use create react app?

    //In command line: 
    //1. npm install -g create-react-app
    //2. create-react-app <appName>
    //3. cd into appName && npm start
    
    
//**-g: stands for global but really means it is a reusable tool.
    
    
//What is the number one rule for the name of your components? 

    //When you create your own component you must start the first letter of the name with a capital letter. PascalCase or sometimes called UpperCamelCase. 
    
    
// How do you import react into your component?

    // import React, { Component } from 'react';  <=== Destructoring. 
    
// What is import doing?

    //Import says bring in code and put it on this variable name.
    //It is the exact same thing as var except it means this is a var but the code or value on it is from another file. 
    
// What is the default file extension on imports?

    //The default file extension on import is .js so you don't have to put it for any javascript files. If you want to import something that is not a javascript file you have to put the file extension like .html or .css.
    

// When importing files into your component how do you start your file path if it is one of your files or if it is installed externally? 

    //Interal: './App.css';
    //External: 'react';

    //. means start where I am in my folder and then look for file called app. './App' without the ./ it means start in the default and the default is node_modules. Things we installed externally. 
    


// How many defaults do you have per file?

    //One. Otherwise your app will implode. 
    
    
// Most React component files follow what structure?

    // import React, { Component } from 'react'; 
    
    // class App extends Component {
    //   render() {
    
    //   }
    // }
    // export default App;
  
  
//**Every component must have a render function. Without it react won't know what to put on the screen. That render function returns html/JSX and that is what react puts on the screen. 

//**Any JS file you can export. If you do export however, it MUST be named. 

//**It is good practice to name files and components the exact same name so your code is more organized. 


// What are some of the differences between html and JSX?

    // ClassName instead of class: work identical but you have to use className because class is a js word and it would break everything. 
    // {} in JSX mean go back to Javascript. 
    
    
// Where do you define state?

    //State is defined in the constructor function.
    this.state = {
        number: 3
    }
    
    
// How do you inject a component into another component?

    // 1. You must import it first. import childComponent from './childComponent';
    // 2. Put the tag into your render function. <childComponent />
  
  

// What does this.setState = {} tell React?

    //setState tells react that it has new state it needs to remember and that it needs to rerender! 
    
    
// React is Unidirectional what does that mean?

    //React data flow is unidirectional, meaning it flows in one direction: from parent to child. The terminology for parent-child component relationship varies, but the nature of the relationship does not.
    
    
// What two types of data do we use in a React app?

    //State & Props
    
    
// Does each component have to use state?

    //React components do not need to have state in order to be rendered or used in a React app. We only use state when we track data that changes in our app.
    
    
// In React what are props?

    //Props are just data displayed in one component that were passed down from another component. Props are one of two ways React handles data. The primary use of props is to allow components to communicate with each other with data and event handlers.
    
                                                                    
// Where is the correct place to set the initial state of a component?
 
  //Setting the initial state of a component needs to happen in the constructor method. If you use the constructor method, you always need to call super() within the constructor method. 
  // Not every component needs state, therefore not every component needs a constructor method. 
  // If you want to use state in a component, you need to set the initial values.
  //You don't import state from other components. The initial values of state are set in that component. If you need to pass the values of state into another component, use props.
  
  
  
// How do you change the value of state?

  //The setState() method needs to be used when you are changing the value of state. This is how React expects changes to state to be made, so altering state in any other way can result in unexpected behavior. this.state() is not a native React method. Because state is an object, we don't use the = assignment operator, instead we use a colon when assigning values. The setState() method is the only way you should be modifying state in React. Using any other method can result in unexpected behavior and poor performance.
  
  

// What is one major reason why React is much faster than other libraries and frameworks?
  
  //React makes changes to their virtual DOM, then updates the real DOM all at once. It only re-renders components whose state has changed, rather than re-rendering every element on the DOM.
  
  
  
  

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


If you use extends in your Component you must invoke super in your constructor. 

option shift f. 

In summary, here's what happens when you try to update the DOM in React:
	.	The entire virtual DOM gets updated.
	.	The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.
	.	The changed objects, and the changed objects only, get updated on the real DOM.
	.	Changes on the real DOM cause the screen to change.