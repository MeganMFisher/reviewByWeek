// Write a function called isNameCorrect that takes in a name as a parameter. If the name is equal to 'Megan' return true else return false.

    function isNameCorrect(name) {
      if(name === 'Megan') {
        return true;
      } else {
        return false;
      }
    }
    isNameCorrect('Jake')
    
    
// What is unique about using 'let' instead of 'var'?

    //In a lot of cases it is a replacement for var but there is a major difference: Block Scope Variable! If you use it in an if statement it will only be accessible inside the if statement. 
    

//Is 6 == '6' true or false? Why?

    //True because double equals checks the value but doesn't check for different data types so 6 == '6' is true even though one is a string and one is a number. 
    
//Is 4 === '4' true or false? Why?

    //False because triple equals checks the value and the data type and since one is a number and one is a string it is false. 
    
// Write a function called ageTracker that takes in an age as the only parameter. If the age is less than 18 return 'Minor'. If the age is between 18 and 60 return 'Adult'. If the age is greater than 60 return 'Senior' else return 'Not valid age'.

    function ageTracker(age) {
      if(age < 18) {
        return 'Minor';
      } else if(age >= 18 && age < 60) {
        return 'Adult';
      } else if(age >= 60) {
        return 'Senior';
      } else {
        return 'Not valid age';
      }
    }
    // ageTracker(27)
    
    
//Write a basic for loop. What are the 3 parts of for loop syntax? 

  // for(var i = 0; i < arr.length; i++)

    // 1. Starting point! Must initially declare a variable and where to start. 
    // 2. Tests Condition! How far to take the for loop. 
    // 3. Ending point! How to increment.
    

//What does Truthy and Falsy mean?

    //When evaluated to true or false within the context of a boolean.
    
    
//What is the basic syntax for a ternary operator?

    //condition ? true : false
    
    
//Write a function called colorChecker that takes in one parameter a color and returns a ternary that tests whether that color is equal to 'yellow' if it is return true else return false. 

  function colorChecker(color) {
    return color === 'yellow' ? true : false;
  }
  // colorChecker('yellow')
  
  
//What does each of these methods do? 

    //.push(): Pushes it onto the end of the array. 
    //.pop(): Takes off the last value of the array. 
    //.shift(): Takes off the first value of the array. 
    //.unshift(): Pushes it onto the array as the first value. 
    //.slice(): Pass in a starting and ending point into slice. If you don't put any parameters into slice it will make a copy of the entire array. Easy way to make a copy of an array if you need to. If you just put in one it will start there and make a copy all the way to the end. IT DOES NOT MODIFY THE ORIGINAL ARRAY. 
    //.splice(): Pass in the starting and how many you want after. DOES MODIFY THE ORIGINAL ARRAY. Also great if you want to remove and replace something in the array. 
    
    
//Write a function called pushNameToArr that takes in a name and the array as a parameters and pushes it to the provided array and returns it. **Be sure to console.log the original array after you invoke it to see the changes.
  var arr = ['Bamm-Bamm', 'Pebbles', 'Fred', 'Wilma', 'Betty'];

function pushNameToArr(array, name) {
  return array.push(name);
}
// pushNameToArr(arr, 'Scooter')
// console.log(arr)


//Write a function classed sliceItUp that takes in an array and returns a copy of the array from index 2 to the end. 
  var array = [1, 2, 4, 6, 2, 56, 2]

function sliceItUp(arr) {
  return arr.slice(2);
}

// sliceItUp(array)


//Write a function called spliceAndReplace that takes in an array and modifies the original array and removes the 'Fred' and replaces it with 'Barney'. **Be sure to console.log the original array after you invoke it to see the changes.
  var arr = ['Bamm-Bamm', 'Pebbles', 'Fred', 'Wilma', 'Betty'];

function spliceAndReplace(arr) {
  return arr.splice(2,1, 'Barney')
}
// spliceAndReplace(arr)
// console.log(arr)


//How do you calculate the length of the given array?
  var arr = ['Bamm-Bamm', 'Pebbles', 'Fred', 'Wilma', 'Betty'];

    //arr.length
    
    // console.log(arr.length)
    
    
//Write a function called loopAndRemove that takes in an array and loops through the array and removes 'Pebbles'. **Be sure to console.log the original array after you invoke it to see the changes.
  var arr = ['Bamm-Bamm', 'Pebbles', 'Fred', 'Wilma', 'Betty'];

function loopAndRemove(arr) {
  for(var i = 0; i < arr.length; i++) {
    if(arr[i] === 'Fred'){
        arr.splice(i, 1)
    }
}
}
// loopAndRemove(arr)
// console.log(arr)


//What is the syntax for looping through an array backwards?

for(var i = arr.length - 1; i >= 0; i--) {
  // console.log(arr[i])
}


//Write a function called backwardsLooping that takes in the given array as the only parameter. Loop backwards through that array and add 1 to each of the items. **Be sure to console.log the original array after you invoke it to see the changes.
  var array = [1, 2, 4, 6, 2, 56, 2];

  function backwardsLooping(arr) {
    for(var i = arr.length - 1; i >= 0; i--) {
      console.log(arr[i])
        arr[i] = arr[i] + 1 //arr[i] += 1
    }
    return arr
  }
  // backwardsLooping(array)
  // console.log(array)
  

//Given the object below add a key of city with a value of 'Bedrock'. **Be sure to console.log the original object after you change it to see the changes.
  var obj = {
    name: 'Betty'
  }

obj.city = 'Bedrock'
// console.log(obj)


// What is a method in it's simpliest definition?

    // Method: Just a function on an object. 
    
    
// Are Objects and Arrays both ordered?

    //Objects aren't ordered. Arrays are ordered.
    
    
// **Dot notation and bracket notation are the only way to access information inside an object. If you do not reference the object first the key value will be be defined. You MUST reference the object in order to see inside of it. 

// **Anytime you are referencing a property with bracket notation you will need to use quotations so it knows you're referencing a property and not a variable. 


//Given the obj add a method called sayFavoriteFood that that alerts 'Pizza'.

var person = {
    myName: 'Barney',
    hairColor: 'Brown',
    sayFavoriteFood: function() {
        alert('Pizza')
    }
}

// person['sayFavoriteFood']()


//How would you access and invoke the second function inside the nestedArray and invoke it?

var person = {
    myName: 'Wilma',
    hairColor: 'red',
    nestedArray: [{
        func: function() {
              console.log('Hello')
              }
        }, 
        {
          func2: function() {
            console.log('Second Hello')
          }
        }]
}

// person.nestedArray[1].func2()


//Finish the function called buildBunnyObj that takes in a name and a color as the parameters. Return an object with a key of bunnyName which is the name passed in as a parameter and a key of bunnyColor which is the color passed in as a parameter.

function buildBunnyObj(name, color) {
    var obj = {
        bunnyName: name,
        bunnyColor: color
    };
    return obj;
}

var skittles = buildBunnyObj('Skittles', 'Rainbow');
// console.log(skittles)

var snowflake = buildBunnyObj('Snowflake', 'White');
// console.log(snowflake)

//**A callback in its simpliest form is a function that is passed in as an argument.

//Finish the below callback function by passing in the callBack function into the callBackHolderFunction as an argument. Then takes that function and console.logs the invokation of it inside the callBackHolderFunction.

function callBack() {
    // console.log('Im a callback');
}

function callBackHolderFunction( cb ) {
    // console.log(cb());

}
callBackHolderFunction( callBack )

// OR

function callBackHolderFunction( cb ) {
    // console.log(cb());

}
callBackHolderFunction( function callBack() {
    // console.log('Im another callback');
} )



//Below you are given an invocation of the function alertObjectName. Your job is to finish the function based on the invocation. You are passed in two arguments an object and a callback function. Alert the value of the name property within the callback function. 

function alertObjectName(obj, cb) {
    cb(obj.name)
}

alertObjectName({name: 'Betty'}, function(obj) {
    // alert(obj)
})


//Below you are given an invocation of the function callbackAddition. Your job is to finish the callbackAddition function based off the three arguments passed into the invocation. You will need to return the invocation of the callback function within the callbackAddition function.


function callbackAddition(number, number2, cb) {
    return cb(number, number2)
}

callbackAddition(12, 55, function(num, num2){
    // return num + num2
})





