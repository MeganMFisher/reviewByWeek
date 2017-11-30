//COMMAND LINE

// What does each of these commands do?

// cd: change directory
// mv: move
// cp: copy 
// touch: make a file
// mkdir: make a folder 
// ls: show folders/files in that directory
// pwd: show path to the folder 



// How would you make a directory called schoolProjects?

  //mkdir schoolProjects
  


// How would you move your index.js from your schoolProjects folder to your schoolAssignments folder? 

  //mv index.js schoolAssignments


//GIT

// What does git init do?

  //It tells git to watch this folder and track any changes. It also allows us to run git commands inside of the folder.



// What does git remote add origin [Repository URL goes here] do?

    //Tells our computer that there is a repo on GitHub for this code and when I push my code I want it to go to that repo. Your computer then knows when you do git push origin master that the origin is pointing to the repo you made on GitHub and it pushes the changes there.




// What do you need to type to see what files have been changed?

  //git status




// What does git diff do?

  //This will show the actual code that has been changed. 




//How do you add your file(s) to the 'staging area'. 

  //git add .   //This is basically a fail safe if you accidentially add something you don't want. You can view items that our staged by running git status.




// What does git commit -m "The sentence I want associated with this commit message" do?

    //This tells your computer: 'Hey, the next time code is pushed to GitHub, take all of this code with it.' The message also specifies what GitHub will display in relation to this commit.




// What does git push origin master do?

    //Your code is now pushed to GitHub. Be sure to include origin master, as this tells GitHub which branch you want to push to, and creates the branch if it doesn't exist yet.



// What does clicking 'fork' on a GitHub repository do?

    //This will essentially copy all of the code from this repository, but make it as a new repository under your account. As you can imagine, you can't push directly to the DevMountain repo, because that would not be secure for DevMountain (anyone could make any changes they want). What you should do is create a fork of this repo, then push to your own fork because it's under your own account.


    
//What do you need to do to take what's on a GitHub repository and essentially download it so you can now make changes to it on your local computer?

    //git clone [the url you copied]
    
    
//JAVASCRIPT

//What is a variable?

  // Named location in Javascript that we can store values. Keyword to declare a variable is 'var'.



//List the data types?

    // Boolean: True/False 
    // Null: null
    // Undefined: undefined
    // Number: 30
    // String: 'Megan' or '30'
    // Object: { color: 'blue' }
    // Array: [ 1, 2, 3 ]
    // Function: function(){}



//What makes an array unique?

  //Lists, 0 index based, square brackets, values separated by commas, can mix data types.



//What side of the object does the property go on?

    //Left side. Value on the right. 


    
//If you need to create a list of all your favorite foods would you use an object or array?

    //Array



// Create an object with at least 2 key/value pairs of your choice and assign it to a variable.

    var name = {
      first: 'Megan',
      second: 'Fisher'
    }



//Create an array with at least 4 values and at least 3 different data types and assign it to a variable.

    var megan = [26, 'female', true, 'purple']
    


//What is the difference between a function expression and a function declaration and give an example of each?

  //If it begins with 'function' it is a declaration. Otherwise, it is an expression.
  

//Function expression:
var expressName = function(){ 
  // console.log('Pebbles') 
}
expressName()

//Function declaration: 
function consoleName(){ 
  // console.log('Fred')
} 
consoleName()


//What is the difference between a parameter and an argument?

    // Arguments are passed in when invoked. Data passed into the function from the function call.  

    // Parameters are the placeholders for information passed into the function. 

  function sayName(name) {  //<==Parameter
    // console.log(name)
  }
  // sayName('megan') //<==Argument


  
//True or False The global scope is 'visible' to all of your code. 

  //True


  
//Do functions have their own scope?

  //Yes



//Write a function that returns a function.


function outer() {
    function inner() {
        console.log('Hello from Inner function');
    }
    return inner;
}
// console.log('here ' + outer())
// var innerfn = outer();
// // innerfn()
// console.log(innerfn())


function mainFunction() {
      return function subFunction() {
            var str = "foo";
            return str;
      }
}
// console.log(mainFunction())
var test = mainFunction();
// console.log(test)
// console.log(test());


// Access the value of the 1 property on the myObj object using bracket notation. 

var myObj = {
  1: 'one'
}
// console.log(myObj[1]) 


// Access the value of the home property on the myObj object using bracket notation.

var obj = {
  home: 'Orem'
}
// console.log(obj[1])
// console.log(obj['home'])


// Write a function called objFunc and pass in the object from above in as the argument. The function should return the value of the home property on the object using dot notation.

function objFunc(obj) {
  // console.log(obj) 
  // console.log(home)
  return obj.home
}
objFunc(obj)



