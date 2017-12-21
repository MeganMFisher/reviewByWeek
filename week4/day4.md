//// CLOSURES

// What can functions return?

    // All the things including functions.



// What is a closure?

    // A function that returns another function.

    // An outer function that returns an inner function. That inner function has access to all the variables that existed in it's lexical environment.

    //The inner function will then remember all the variables it had access to within the outer function even after the outer function has been invoked. 

    // A function within another function.

    // Takes a snapshot of its scope or lexical environment at the time it is invoked. 
    


// Give an example of a closure?

    function closure() {
      let num = 0;
      return function() {
        return ++num
      }
    }

    let one = closure()
    one()
    let two = closure()
    two()
    two()
    two()



// What is the difference between ++num and num++?

    // ++ before will increment the value and then return.

    // ++ after will return the value then increment it.





// Make the following code work:

    function mathStuff(num) {
      return function(num1) {
        return num1 + num;
      }
    }

    // let add = mathStuff(10)
    // add(10) // returns 20




// What are the benefits of using a closure?

    // It allows us to keep private variables and public variables. 

    // It is a more controlled environment.

    // Prevents potential bugs and issues in your code because you aren't using global variables.

    // Keeping your code DRY.





// Use closure to create a function that will take a pizza order.

      function pizzaOrder() {
        let toppings = []
        return function(top) {
          toppings.push(top)
          return toppings
        }
      }

      let james = pizzaOrder()
      james('all the things')





// MODULE PATTERN

// What is the module pattern?

    // Allows us to use public and private methods & variables along with shielding parts of our code from the global scope.

    // Example: Private function invoked by the public one.

    // Limited access and very controlled. 

    // The only difference is returning an object with methods rather than returning a function.




// Write an example of the module pattern?

    function closuring() {
      let privateVar = 'this is private'
      function privateFn(str) {
        privateVar = str
      }

      return {
        write: function(str) {
          privateFn(str)
        },

        read: function() {
          return privateVar
        }

      }
    }

    let publicWord = closuring()
    publicWord.read()

    publicWord.write('changed')
    publicWord.read()




// Create a calculator using closures and the module pattern.

    function calculator() {
      let value = 10

      return {
        add: function(num) {
          return value += num 
        },
        subtract: function(num) {
          return value -= num 
        },
        divide: function(num) {
          return value /= num 
        },
        multiply: function(num) {
          return value *= num 
        }
      }
    }
    
    let calc = calculator()
    calc.divide(2)





//// CONTEXT 

// What is context?

    // Context is the surrounding information that gives understanding and clarity.

    // 'this' will always be an object. If it is not it will break.



// What are 3 ways to determine context?

    // Explicit
    // Implicit
    // Default

    // It will first look for explicit context to give the value to 'this' it will then go to implicit then default. 

    // Default is the window. We don't want that.

    // Be sure to always use explicit or implicit context. 



// What is implicit context?

    // Whatever is left of the dot when the function is invoked. Doesn't matter where it is declared, defined or where the function lives it only matters when it is invoked.



// How do you use explicit context?

    //.call(), .apply(), .bind()

    function binding() {
      return this 
    }

    let value = {
      num: 123453
    }

    let newBinding = binding.bind(value)
    newBinding()




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


    // 'This dog is white, is 8 years old, and has a low energy level.'

    // Because the context being used here is implicit. Since there is an object left of the dot.




// What will be the value of this code below when uncommented?

    let description = dog.description
    // description() 

    // 'This dog is undefined, is undefined years old, and has a low energy level.'

    // This is using the default context and there is no color, age, or energy properties on the window. 




// What would happen if I added 3 global variables named color, age and energy?

    let color = 'black'
    let age = 12
    let energy 12

    // description() 

    // 'This dog is black, is 12 years old, and has a high energy level.'

    // It is using default context to get the value of this off the window context. 





// What is the order of priority when defining 'this'?

    // Explicit
    // Implicit
    // Default




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


    // 'heeeeeyyyy'

    // Because even though there was a value on the original object when we invoked it we bound it to the newValue and that takes precident. 





//// CONSTRUCTOR FUNCTIONS 

// Write a basic class function?

    class Betty {
      constructor() {
        this.age = 23
      }
    }

    new Betty;

    // A class is basically a constructor function.




// A car object builder example as just a function.

    function carBuilder(make, model) {
      let car = {}
      car.make = make;
      car.model = model;
    }

    carbuilder('Toyota', 'Matrix')




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

      // If you add return to a constructor method you will not get what you think and it will break things. 
    }

    // Using the 'new' operator builds an new instance of an object (blueprint for object  contained in the function)
    // 'new' also sets the context for the 'this' keyword.
    // let mustang = new Car();




// What happens when you don't use the 'new' keyword?

    // With constructor function you put the properties on the window object instead of the 'this' object. 

    // If you don't use a new keyword with classes it will just break. 




//// PROTOTYPES 

// Review of prototypes on classess.

    // Anytime you write a function inside of a react class you are writing a prototype. 

    // Prototype methods will allow us to have one copy of it. It is a way to keep your code dry. 

    // Prototype is an object that is accessible to all the things. .push(), .slice() etc are all methods on the prototype object. 

    // Really great way to save on memory. 



// What happens when you code a method inside a constructor function?

    //Good practice to capitalize the name but not required.

    function WithMethod() {
 
    }

    WithMethod.prototype.fn = function() {
        return 'cool'
      }

    let vari = new WithMethod()
    vari.fn()

    //'cool'

    let vari = new WithMethod()
    let vari2 = new WithMethod()
    vari.fn === vari2.fn
    // false



// Write an example of a prototype on an array that returns the first item in the array.


    Array.prototype.newFn = function() {
      return this[0]
    }

    let arr = [1,32,5]

    arr.newFn()





//// ARROW FUNCTIONS

// How do arrow functions handle 'this'?
    
    // An arrow function's 'this' takes on the value of what 'this' would be in it’s surrounding scope at the time that it was created as opposed to the time that it was invoked like other functions (because of this, explicit binding will never work).



// Paste this code in your console and invoke the method 'context':

    let notArrow = {
      context: function() {
        return this
      }
    }



// What was the value?

    notArrow.context() // notArrow {}
 


// Now paste this code in the console and invoke the method 'context':
 
      let arrow = {
        context: () => {
          return this
        }
      }

// What was the value?

    arrow.context() // window

    Arrow functions don't care about the context.




// What will be the value of the code below when it's pasted in the console and why?

    let nestedArrow = {
        value: 'abc',
        createArrow: function() {
            return () => this;
        }
    }
    let arrowFn = nestedArrow.createArrow()
    // arrowFn()

    //{ value: 'abc', createArrow: [Function] }





// What will be the value of this code below and why?

    let removedFunction = nestedArrow.createArrow
    // removedFunction()

    // [Function]



// What is the difference between and arrow function and a regular function when it comes to context?

    // With an arrow function the context of that function is determined wherever the function is declared which is different from a regular function which context is determined where the function is invoked. 

































