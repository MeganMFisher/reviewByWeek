//indexOf: Write a function called getIndex that takes in an array and a name as the parameters. It should return the index of the name within that array.
  var array = ['Betty', 'Fred', 'Pebbles']
  
  
  

//indexOf: Write a function called getIndex that takes in an string and a letter as the parameters. It should return the index of that letter within that string.
  var string = "Bamm-Bamm has anger issues"
  
  


//True or False Objects and arrays are stored in memory and variables can be references to those values?



//Given the code below would the console.log show as true or false? Why?
  var array = ['Betty', 'Fred', 'Pebbles']
  var names = array
  // console.log(names === array)
  
  
  
//Given the code below would the console.log show as true or false? Why?
  var array = ['Betty', 'Fred', 'Pebbles']
  var names = array
  names = array.slice(); 
  // console.log(array === names)
  
  
//True or False Objects and arrays are NOT stored in memory and variables can be references to those values. 


//**The map() method creates a new array with the results of calling a provided function on every element in the calling array

//What three arguments does a .map() take?



//Write a function call mappingIt that takes in an array as the argument and divides every number in the array by 2. 
  var arr = [1,2,3,4] 
  
  
//**The filter() method creates a new array with all elements that pass the test implemented by the provided function.

//What three arguments does a .filter() take?



//What would each of the these blocks of code using .filter() return?

  var array = ['Betty', 'Fred', null, 'Pebbles', '']

array.filter(function(elem, index, array) {
    return true;  
})

array.filter(function(elem, index, array) {
    return false; 
})



//Write a function call greaterThanFilter that takes in an array of numbers and returns only those that are greater than 20 using .filter();
  var array = [180,20,3,46]
  
  


//Write a function called filterLength that takes in an array of names and returns only those with a length longer than 6;
  var array = ['Betty', 'Wilma', 'Fred', 'Pebbles', 'Bamm-Bamm', 'Barney']


//**The reduce() method applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value.

 //True of False Reduce is called with a function and a value?
 
 

//What are the four arguments that reduce callback function takes?
 
 
 
 
//Write a function called getTotal that takes in an array as the only parameter. Using reduce get the total of the following array.
  var totalArr = [1,23,3,24,5,46,7,130,2,50];
  
  

//Write a function call getPostiveTotal that takes in an array as the only parameter. Using reduce calculate the total of only the positive numbers of this array
  var totalPositive = [100,20,-35,14,-5,6,75,-140,-2,56];



//True or False Classes are functions that make objects in Javascript?



//Below you have a block of code that creates an animal object that isn't working. Fix the code so that it when consoling hippo and flamingo variables you can see their type and color. 

// class Animal {
//   constructor(type, color) {
//     type = type;
//     color = color;
//   }
// }

// var hippo = Animal('Hippo', 'Purple')
// console.log(hippo)
// var flamingo = new animal('Flamingo', 'Pink')
// console.log(flamingo)




//Make a class to keep track of all your customers. 

// Each customer has a:
// - firstName
// - lastName
// - email
// - address
// - phoneNumber

// Call your class Customers and receive all the data in the constructor in the order listed.

// Each customer can:
// - orderShipAddress
//     - This returns a string equal to the customer's first name +     last name + the words 'wants their order shipped to: ' + their address
//Example - "Fred Flintstone wants their order shipped to: 123 Bedrock Rd."


//Use object destructuring to save the property values from the object into new variables.

var exportsObj = {
  password: 'keyboardpoundlajfjelfajf',
  secret: 'superSecretSecret',
  authenticationString: 'kdfikdkdkdkdijekf',
  connectionString: 'afdkdiojfelakjelkfnedjafjefjaefdafd',
}


// Write a function called largestNumber that will take a destructured object as it's parameter. Pass in the numbers object into your function. Find the largest number of the three and return that number.
  var numbers = {
    one: 123456,
    two: 245345,
    three: 453223
  }