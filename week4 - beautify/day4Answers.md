//// CLOSURES

// What can functions return?



// What is a closure?




// What is the difference between ++num and num++?




// Make the following code work:
    // let add = mathStuff(10)
    // add(10) // returns 20



// What are the benefits of using a closure?



// Use closure to create a function that will take a pizza order.




// MODULE PATTERN --- Allows us to use public and private methods & variables along with shielding parts of our code from the global scope.
// Example: Private function invoked by the public one.




// Create a calculator using closures and the module pattern.




// Create a bank account where you can add and remove funds.



//// CONTEXT 

// What is context?

    // Context is the surrounding information that gives understanding and clarity.



// What are 3 ways to determine context?




// What will be the value of the code below when uncommented?

    let dog = {
      color: 'white',
      age: 8,
      energy: 4,
      description: function() {
        return `This dog is ${this.color}, is ${this.age} years old, and has a ${this.energy > 5 ? 'high' : 'low'} energy level.`
      }
    }

    // dog.description()




// What will be the value of this code below when uncommented?

    let description = dog.description
    // description() 




// What would happen if I added 3 global variables named color, age and energy?





// What is the order of priority when defining 'this'?




// What will be the value of the code below?

    let implicit = {
        value: 'hi',
        sayHi: function() {
            return this.value
        }
    }

    let newValue = { value: 'heeeeeyyyy' }

    let explicit = implicit.sayHi.bind(newValue)
    // explicit()



//// CONSTRUCTOR FUNCTIONS 

// Classes review. Syntactical sugar for days and days.


// A car object builder example as just a function.

// Now a constructor function.

    function Car() {
      // 'this' refers to the new object that is being constructed.
      // we are using dot notation to add make & model properties to the new object.
      
      // this = {} <--- IMPLIED
        console.log(this)
        this.make = 'Ford'
        this.model = 'Mustang'
        console.log(this)
      // return this <-- IMPLIED
      
      // The new object gets automatically returned, we don't need to use a return statement.
    }



// Using the 'new' operator builds an new instance of an object (blueprint for object  contained in the function)
// 'new' also sets the context for the 'this' keyword.
// let mustang = new Car();




// What happens when you don't use the 'new' keyword?


// Classes help prevent this.


//// PROTOTYPES 

// Review of prototypes on classess.




// What happens when you code a method inside a constructor function?




// What happens when you code a method as a property on the prototype?



//// ARROW FUNCTIONS

// *** How do arrow functions handle 'this'?
    
    // An arrow function's 'this' takes on the value of what 'this' would be in it’s surrounding scope at the time that it was created as opposed to the time that it was invoked like other functions (because of this, explicit binding will never work).



// Paste this code in your console and invoke the method 'context':

    let notArrow = {
      context: function() {
        return this
      }
    }
 



// What was the value?
// Now paste this code in the console and invoke the method 'context':
 
      let arrow = {
        context: () => {
          return this
        }
      }




// What was the value?





// What will be the value of the code below when it's pasted in the console and why?

    let nestedArrow = {
        value: 'abc',
        createArrow: function() {
            return () => this;
        }
    }
    let arrowFn = nestedArrow.createArrow()
    // arrowFn()




// What will be the value of this code below and why?

    let removedFunction = nestedArrow.createArrow
    // removedFunction()