//Below is a .bind() example that is current broken. Fix the block of code to so that it 
//returns the name fred in your console. 

var myName = function() {
   return this.name; //to access anything in the object you must use this.key
}

var fred = {
    name: 'fred',
    age: 36
}

var sayName = myName.bind(fred);  //the function goes first then the object is passed in as a parameter into the .bind().
sayName() //sayName is a copy of the myName function that is now bound with the object that you then invoke.




// What can be passed as props from one component to another?

    //Arrays, functions, object, strings, other components.
    // For components to communicate with each other in React, we use props, and since we can treat props like any other object in JavaScript, this means we can pass basically anything as a prop from one component to another.
    
    
    
// How do we pass this.props.children from a parent component to a child component?


    //<ComponentName data={ this.state.variableName }  />
    
    

// How does the child component access the props from the parent component?

    //{ this.props.variableName } //Its not what the parent calls it its what the parent tells us to call it. 
    
    //In Parent Component: 
    // this.state = {
    //   favColor: 'Pink'
    // }
    
    //<ChildComponent color={this.state.favColor} />  
    
    //In Child Component: { this.props.color } <= if inside JSX   this.props.color <= if not in JSX just in render.
  


// How do you bind a function in your contructor function?

      //this.functionName = this.functionName.bind(this)
      ////TypeError: Cannot read property 'keyName' of undefined? A common error for when you forget to bind your functions that are trying to access state.
      
      
  
// What is an event listener and give an example of one?

    //onClick, Event listeners are used to moniter user actions and respond to them accordingly -- they are not related to faster component-to-component communication.
    
    
    
// How are even listeners and state related in a React app?

    //Event listeners are often used to trigger state changes in an app. While event listeners are a common way to trigger state updates, React does not expect those updates to be triggered by event listeners. Event listeners existed long before React did.


// What does the component lifecycle componentWillReceiveProps do?

    //It watches the parent component and when the parent component makes a change on props that doesn't trigger a rerender the child component will still be able to receive it even though it hasn't been rerendered because it is componentWillReceiveProps is watching for changes to props.

    //Only called when the props have changed and when this is not an initial rendering. componentWillReceiveProps enables to update the state depending on the existing and upcoming props, without triggering another rendering.
    //We are now in a fun place, where we have access to both the next props (via nextProps), and our current props (via this.props)

    
// componentWillReceiveProps: function(nextProps) {
//   this.setState({
//     // set something 
//   });
// }



// Can componentWillReceiveProps call setState?

    //Yes it can. 
    
    
    
//Bind Example   
    
class App extends Component {
   constructor() {
    super();
    this.state = {
      favColor: 'maroon'  
    };

    this.updateColor = this.updateColor.bind( this ); //To bind we put the function(prototype method) to the left of the .bind then pass in an object as the parameter. 'this' is used as the argument so that updateColor can access what is inside the this.state object. 
   }

updateColor() {
  let updatedColor = '';
  if(this.state.favColor === "maroon") {
    updatedColor = 'purple';
  } else {
    updatedColor = 'maroon';
  }
  this.setState({
    favColor: updatedColor
  })
} //In order for the updatedColor function to have access to what is on state we must bind them together in the constructor function. Without binding them it will not know where to look for this.state and give you an error.

render() {
    return (
      <div>
          <p>My favorite color is { this.state.favColor }</p>
          <button onClick={ this.updateColor }>Update Color</button>
      </div>
    )
  }
}



export default App;

//this.updateColor = this.updateColor.bind( this ); returns a new function, in which references to this will refer to something. This is a way of saving the current value of this, which is in scope during the call to the constructor, so that it can be used later when the function is called.
//If your functions don't require access to the state of your component, then sure, you don't need to bind them.
