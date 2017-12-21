// When should you use redux?

  //Redux is complex so we only do it when we need it. If the parent can pass to its child then don't put it on redux. Use it when you need to pass state sideways at the top etc. 
  
  
  
// Can you use redux in other libraries and frameworks?

  //Yeah Angular, node etc can all use it. It is just a pattern. 
  
  
  
// What does React-Redux do?

  // React-redux manages all the talking between react and redux. Redux itself manages the box(store/reducer).


// What does Object.assign() have to do with redux?

  //It makes a new empty object and we merge the state object with the third parameter object and copy it to the new one as well. Brand new empty object that replaces the original object. React JS checks to see if they are the same box but doesn't look inside the box so if the memory allocation is the same on both objects it won't tell tell the components to rerender. You must use Object.assign() to create a whole new memory allocation to create a new box with the changes.
  
  
  
// What does every action object you push into Redux have to have?

  //Every action object you want to push into redux must have a type property. The type is used within the reducer switch statement case. 
  
  //Redux promise middleware: Is the only time you HAVE to use payload as the second parameter. 
  


// What is an Action Creator?

    //A function that builds an object. 
    
    function updateAge(age) {
      return {
          type: "UPDATE_AGE",
          payload: age
      }
    }
    
    

// The reducer function takes two parameters what are they?

    //State and an Action.
    
  
    
// What do you use inside the reducer function to check the types of the actions which are being passed in?

    // A switch statement. The type is the case. 

    function reducer(state, action) {
    //SINGLE POINT OF TRUTH
      switch (action.type) {
          case "UPDATE_AGE":
              return Object.assign({}, state, { age: action.age })
      }
    }


// What do you need to import into your Index.js to make Redux work in your application?

  //import store from './store'
  //import { Provider } from 'react-redux'
  
  //Putting the provider here in the index.js gives it top level access to the whole app so it can tell React to render when needed.
  
  //The store is your box where your state is stored. 



// What is the provider?

  // It comes from react-redux. Meaning it is going to watch for our state to change in the store and when it does it will tell the components to rerender all the things that need rerendering. Helps us force that rerender on change and helps direct those changes to the right pieces.
  
  
  
// What do you need to import into and export from your store.js?

    // import { createStore } from 'redux'; //Notice redux, not react-redux
    // import reducer from './reducer';
    
    //export default createStore(reducer); //export the store so the index.js can use it.
     
    

// What do we put into our reducer.js file? 

    //CONSTANTS
    const UPDATE_NAME = "UPDATE_NAME";  //Types usually done like this.
    //ACTION BUILDERS
    export function updateName(name) {
        return {
            type: UPDATE_NAME,
            name //es6 shortcut for assigning a variable to an object with the same property name as the variable name
        }
    }
    //REDUCER
    export default function (state = initialState, action) { //Will only use initialState when the state variable is null or undefined. So any time after the initialstate is placed it will you the state variable not the initialState since state is no longer undefined. 
        switch (action.type) {
            case UPDATE_NAME:
                return Object.assign({}, state, { name: action.name })
        }
    
        return state;
    }
    
    

// How does the provider, store, and reducer all work together?

    //The reducer takes in the incoming change from the component and creates a new state from the old state and the action. The store holds the new state. Provider is going to watch for our state to change in the store and when it does it will tell the components to rerender all the things that need rerendering. 
    
    //React: Uses Provider. 
    
    //Provider: Uses the store. Watches the state at a global level and rerenders components when needed based off the new state in the store. 
    
    //Store: Uses the reducer(s). Is the box that holds the state with all its key value pairs. 
    
    //Reducer: The reducer takes in a state and action and returns a new state. It manages your box.
    
    
    
// What do we need to import into your component to use redux?

    //import { connect } from 'react-redux' // To make this component work we need to 'connect' it with our top level redux store
    //import { updateName, addPerson } from './reducer' //import action creator functions from reducer
    
    

