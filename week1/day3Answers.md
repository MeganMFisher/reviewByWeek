//indexOf: Write a function called getIndex that takes in an array and a name as the parameters. It should return the index of the name within that array.
  var array = ['Betty', 'Fred', 'Pebbles']

function getIndex(arr, name) {
  return arr.indexOf(name)
}
getIndex(array, 'Fred')

//indexOf: Write a function called getIndex that takes in an string and a letter as the parameters. It should return the index of that letter within that string.
  var string = "Bamm-Bamm has anger issues"

function getIndex(str, letter) {
  return str.indexOf(letter)
}
getIndex(string, 'g')


//True or False Objects and arrays are stored in memory and variables can be references to those values?

    //True


//Given the code below would the console.log show as true or false? Why?
  var array = ['Betty', 'Fred', 'Pebbles']
  var names = array
  // console.log(names === array) //True because they are both pointing at the same array.


//Given the code below would the console.log show as true or false? Why?
  var array = ['Betty', 'Fred', 'Pebbles']
  var names = array
  names = array.slice(); 
  
  // console.log(array === names) //False not the same because they are two different arrays in memory because slice creates a copy which makes a new memory of that array.
  
  
//True or False Objects and arrays are NOT stored in memory and variables can be references to those values. 

    //False


//**The map() method creates a new array with the results of calling a provided function on every element in the calling array  
    
//What three arguments does a .map() take?

    //1. Current Value (the element)
    //2. Index
    //3. Array
    
    
//Write a function call mappingIt that takes in an array as the argument and divides every number in the array by 2. 
  var arr = [1,2,3,4] 

function mappingIt(arr) {
    return arr.map((e) => {
      return e /= 2
    })
}

// mappingIt(arr)



//**The filter() method creates a new array with all elements that pass the test implemented by the provided function.

//What three arguments does a .filter() take?

    //1. Current Value (the element)
    //2. Index
    //3. Array



//What would each of the these blocks of code using .filter() return?

  var array = ['Betty', 'Fred', null, 'Pebbles', ''];

array.filter(function(elem, index, array) {
    return true;  //['Betty', 'Fred', null, 'Pebbles', ''] 
})

array.filter(function(elem, index, array) {
    return false; //[] 
})


//Write a function called greaterThanFilter that takes in an array of numbers and returns only those that are greater than 20 using .filter();
  var array = [180,20,3,46]

function greaterThanFilter(arr) {
  return arr.filter(function(elem, index, array) {
    return elem > 20
})  
}
// greaterThanFilter(array);



//Write a function called filterLength that takes in an array of names and returns only those with a length longer than 6;
  var array = ['Betty', 'Wilma', 'Fred', 'Pebbles', 'Bamm-Bamm', 'Barney']
  
  function filterLength(arr) {
    return arr.filter(function(elem, index, array) {
      return elem.length > 6
    })
  }
  // filterLength(array)
  
  
  
//**The reduce() method applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value.
 
 //True of False Reduce is called with a function and a value?
 
    //True Syntax: arr.reduce(callback[, initialValue])
    
    
//What are the four arguments that reduce callback function takes?

    // 1. The Value of the previous return from the iterative function
    // 2. Current Value (The current Element)
    // 3. Index
    // 4. Array 


//Write a function called getTotal that takes in an array as the only parameter. Using reduce get the total of the following array.
  var totalArr = [1,23,3,24,5,46,7,130,2,50];

function getTotal(arr) {
  return arr.reduce(function(sum, current) {
    return sum + current;
  }, 0);
}
// getTotal(totalArr)

//Write a function call getPostiveTotal that takes in an array as the only parameter. Using reduce calculate the total of only the positive numbers of this array
  var totalPositive = [100,20,-35,14,-5,6,75,-140,-2,56];

function getPostiveTotal(arr) {
  return arr.reduce(function(sum, current) {
    if (current > 0) return sum + current;
    else return sum;
  }, 0);
}
// getPostiveTotal(totalPositive)


//True or False Classes are functions that make objects in Javascript?

    // True  Classes are a tool for building similar objects over and over again. They are a construct that helps your organize your code.
    
    
//Below you have a block of code that creates an animal object that isn't working. Fix the code so that it when consoling hippo and flamingo variables you can see their type and color.

class Animal {
  constructor(type, color) {
    this.type = type;
    this.color = color;
  }
}

var hippo = new Animal('Hippo', 'Purple')
// console.log(hippo)
var flamingo = new Animal('Flamingo', 'Pink')
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

class Customer {
  constructor(firstName, lastName, email, address, phoneNumber) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.email = email;
    this.address = address;
    this.phoneNumber = phoneNumber;
  }
  
  orderShipAddress() {
    return this.firstName + ' ' + this.lastName + ' wants their order shipped to: ' + this.address;
  }
  
}

var fred = new Customer('Fred', 'Flintstone', 'Fred@aol.com', '123 Bedrock Rd.', '123-345-567');
// console.log(fred)
// fred.orderShipAddress()



//Use object destructuring to save the property values from the object into new variables.

var exportsObj = {
  password: 'keyboardpoundlajfjelfajf',
  secret: 'superSecretSecret',
  authenticationString: 'kdfikdkdkdkdijekf',
  connectionString: 'afdkdiojfelakjelkfnedjafjefjaefdafd',
}

var { password, secret, authenticationString, connectionString } = exportsObj;

// console.log(password)
// console.log(secret)


// Write a function called largestNumber that will take a destructured object as it's parameter. Pass in the numbers object into your function. Find the largest number of the three and return that number.
  var numbers = {
    one: 123456,
    two: 245345,
    three: 453223
  }


function largeNumbers({one, two, three}) {
  return Math.max(one, two, three);
}
largeNumbers(numbers)
