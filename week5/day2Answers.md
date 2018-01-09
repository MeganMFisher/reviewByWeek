// What is Underscore.js?

    //Underscore is a library that can help us clean up our code.  It has many helpful functions in it.  Many of which were so helpful, they have found their way into the core of JavaScript (map, filter, forEach, reduce, find) There are others that are under review for being incorperated into the core JavaScript language.
    
    //You can easily manipulate, sort and display data in the various ways necessary to run a successful site. Underscore provides over 80 functions, which do everything from basic mapping of arrays (map, of course) to creating "flexibly-numbered lists of integers" (range), to inverting the keys and values of an object (invert). 

    //If you’re manipulating and transforming data in any reasonably complex way, an Underscore style library will help you write performant readable code easier than you could with what Javascript natively provides. Underscore performs better than native browser functional methods, and for complex data manipulations they’re significantly more readable than a series of for loops. It lets you write code that’s fast and reads like a description of what you intend to have happen.
  
    //It is JS so anywhere you use JS you can use Underscore.js. Node, React etc... 
    
    //It’s used on sites like Reddit, Huffington Post, and LinkedIn
  
    //ES5 added .map, .filter, .find etc from underscore.
    
    
  
// What are the benefits to using underscore.js?

    //More efficient and better code, a lot of times it is shorter, easier to read. Jeremy has never used a project in production that didn't use Underscore or Lodash. 
    
    //Some of the benefits are less apparent in smaller and simpler code chunks. But, as the complexity of the code increases, this is where Underscore really shines as the useful toolbox that it is.
    
    //Using the framework can allow you to be more expressive in your code, improving readability for all those that may have to eventually dig through your code.
    
    //You can drastically transform your arrays, objects, and functions with only a line or three of code.
    
    //Underscore sometimes beats native functions in terms of speed.
    
    //It is way easier to memorize shorter lines of code that underscore allows us to do rather than longer regular Javascript lines. When are you more likely to have logic issues, typoes, etc on one line of code or 100 lines of code. 
    
    //Elimitates what takes us 4,5,6 lines of code to figure out what is happening in a block of code by starting with exactly what it is doing _.map, _.filter etc. 

    // You are able to use a lot of methods on both arrays and objects (map on an object!!)

    // Can deal with data easily in a just a few lines of code. 

    // The methods you have access to are names very clearly to make your code even more readable. 





//What makes Underscore so rad?


    //Methods on objects, instead of just Arrays. .map on objects think of the possibilites. 
  
    //**** You can use _.map, _.filter, _.reduce, _.find, _.contains on an object!!



      let person = {
        firstName: 'Wilma',
        lastName: 'Flintstone',
        hairColor: 'red',
        maidenName: 'Pebble'
      }
      
      var mapPerson = _.map(person, e => {
                console.log(e)
       })
       
       ///////////
    
      var filterPerson = _.filter(person, e => {
                console.log(e)
       })
  
      ///////////  
    
      let scores = {
        Fred: 19,
        Betty: 25,
        Pebbles: 34,
        Wilma: 23
      }
      
      var reduceScores = _.reduce(scores, (memo, num) => { 
          return memo + num
       });

      console.log(reduceScores) //101 
      
      ///////////
      
      
      var findScore = _.find(scores, num => {
        return num > 30
      })
      
      console.log(findScore) // 34
      
      
      ///////////
      
      let scores1 = {
        Fred: 19,
        Betty: 25,
        Pebbles: 34,
        Wilma: 23
      }
      
      
      var findScore = _.contains(scores1, 23)
      
      console.log(findScore) //True  Like includes().

    
    
// What does _.groupBy() do?

    // Group By lets us take an array of objects, and group then into groups based on a proprty. It will allow us to organize groups. 
    
    
    
// Below is an object of monthly temperatures. Group the temperatures by the month and set to a variable called groupedTemps. 


      let temperatures = [
          {month: 'March', temp: 62},
          {month: 'April', temp: 59},
          {month: 'March', temp: 67},
          {month: 'April', temp: 73},
          {month: 'May', temp: 91},
          {month: 'March', temp: 54},
      ]
      
      //code here
      
      let groupedTemps = _.groupBy(temperatures, 'month');
      
      console.log(groupedTemps)  //{March: Array(3), April: Array(2), May: Array(1)}

    
    

// What does _.union() do?

      // Union lets us take 2 arrays, and create a new array that only has 1 entry for each duplicated entry.
    
    
    
    
// Below are two arrays each containing a list of animals. Use union to combine the two and set it to a new array called animals. 

    let array1 = ['Tiger', 'Leopard', 'Elephant', 'Duck', 'Penguin', 'Bear']
    let array2 = ['Horse', 'Bear', 'Leopard', 'Baboon', 'Hawk', 'Tiger']

    var animals = _.union(array1)
    
    console.log(animals) //["Tiger", "Leopard", "Elephant", "Duck", "Penguin", "Bear", "Horse", "Baboon", "Hawk"]





// What does _.intersection() do?

    // Intersetction lets us take two arrays, and create a new array that only contains shared elements.
    
    
    
// Below are two arrays each containing a list of animals. Use Intersection to combine the two and set it to a new array called animals. 

    let array1 = ['Tiger', 'Leopard', 'Elephant', 'Duck', 'Penguin', 'Bear']
    let array2 = ['Horse', 'Bear', 'Leopard', 'Baboon', 'Hawk', 'Tiger']

    var animals = _.intersection(array1, array2)
    
    console.log(animals)  //["Tiger", "Leopard", "Bear"]




// What does _.difference() do?

  //Returns the values from array that are not present in the other arrays.



// Is parameter order important with _.difference()? 

    //Yes, it will only return the values of the first array that is passed in that are not in the second array. It will not return values in the second array that are not in the first. 
    
    

// Below are two arrays each containing a list of animals. Use difference to get all of the values in array2 that are not in array1  

    let array1 = ['Tiger', 'Leopard', 'Elephant', 'Duck', 'Penguin', 'Bear']
    let array2 = ['Horse', 'Bear', 'Leopard', 'Baboon', 'Hawk', 'Tiger']

    let difference = _.difference(array1, array2)
    let difference2 = _.difference(array2, array1)
    
    console.log(difference)  //["Elephant", "Duck", "Penguin"]
    console.log(difference2) //["Horse", "Baboon", "Hawk"]



// What does _.memoize() do?

    //Memoize lets us take a function that takes a lot of time to run.  And memeorize results for that function, so if we run the function with the same parameters again, it will used the momorized results instead of making the calculation again.



// MEMOIZE EXAMPLE 




// What does _.shuffle() do?


    //Returns a shuffled copy of the array.
    
    
    let ary = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20];
    let shuffled = _.shuffle(ary);
    console.log(shuffled, ary);
    
    
    //Original not modified: [15, 3, 8, 6, 12, 14, 9, 5, 4, 17, 2, 11, 16, 20, 18, 13, 1, 19, 10, 7]
    //Shuffled array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]

      let scores = {
        Fred: 19,
        Betty: 25,
        Pebbles: 34,
        Wilma: 23
      }
      
      var shuffledScores = _.shuffle(scores)
      
      console.log(shuffledScores)  //[25,34,19,23]  //Can use it on objects too. Will turn values into an array. 



// Below is an array. Shuffle it and set in to a new variable called shuffledArr. 

    let array = ['Tiger', 'Leopard', 'Elephant', 'Duck', 'Penguin', 'Bear']

    var shuffledArr = _.shuffle(array)
    
    console.log(shuffledArr) // [ "Bear", "Tiger", "Elephant", "Leopard", "Penguin", "Duck"]




// What does _.pluck() do?

    //Pluck lets us take an array of objects.  And create an array that consists of the property from each object that we specify.
    
    // One of the most convenient of Underscore's functions, pluck creates an array of property values. This is excellent for displaying or manipulating subsets of data.
    
    
// Below is an array of animal objects. Use pluck to get back just the type properties.

  var animalArray = [{name: 'Timonthy', type: 'Tiger', color: 'Orange'}, {name: 'Wonda', type: 'Hippo', color: 'Purple'}, {name: 'Larry', type: 'Antelope', color: 'Tan'}]

  var animalTypes = _.pluck(animalArray, 'type')

  console.log(animalTypes) //["Tiger", "Hippo", "Antelope"]
  
  
  

// What does _.throttle()  do?

  //Creates and returns a new, throttled version of the passed function, that, when invoked repeatedly, will only actually call the original function at most once per every wait milliseconds. Useful for rate-limiting events that occur faster than you can keep up with.

  
    
    // <button onClick="throttled()">pushMe</button>
    // <button onClick="unthrottled()">pushMe2</button>
    
    <!-- //Throttled function:     -->
    var throttled = _.throttle(()=>{
      alert('Hi'); 
    }, 5000)
    
    //Won't let them click it more then every 5 seconds. Awesome for submitting payments so they don't accidently submit multiple payments by hitting the button again. 
    
    <!-- //Unthrottled function:  -->
    function unthrottled = ()=>{
      alert('Hi');
    }
    



// What does _.debounce() do?

    //Creates and returns a new debounced version of the passed function which will postpone its execution until after wait milliseconds have elapsed since the last time it was invoked. Useful for implementing behavior that should only happen after the input has stopped arriving. For example: rendering a preview of a Markdown comment, recalculating a layout after the window has stopped being resized, and so on.

    //At the end of the wait interval, the function will be called with the arguments that were passed most recently to the debounced function.



    // <button onClick="debounced()">pushMe3</button>

    var debounced = _.debounce(()=>{
      alert('Debounced');
    }, 1000)



//Typically used on input boxes. It will make sure your user is done entering into the search input before it is sent off. It will be slightly slower for that first request but it won't have to make as many requests. 




// What does .once() do?

    //Creates a version of the function that can only be called one time. Repeated calls to the modified function will have no effect, returning the value from the original call. Useful for initialization functions, instead of having to set a boolean flag and then check it later.
    
    var initialize = _.once(createApplication);
    initialize();
    initialize();
    // Application is only created once.


// What does _.negate() do?

    //Returns a new negated version of the predicate function.
    
    var isFalsy = _.negate(Boolean);
    _.find([-2, -1, 0, 1, 2], isFalsy);
    => 0


// What does _.invert() do?

    //Returns a copy of the object where the keys have become the values and the values the keys. For this to work, all of your object's values should be unique and string serializable.

    _.invert({Moe: "Moses", Larry: "Louis", Curly: "Jerome"});
    => {Moses: "Moe", Louis: "Larry", Jerome: "Curly"};
    
    
          let temperature = {
            month: 'March',
            day: 1
            temp: 62
          }
      
      var invertedTemp = _.invert(temperature)
      
      console.log(invertedTemp) //{1: "day", 62: "temp", March: "month"}
    
    
////////////////////////////////////////////////////////////


const purchases = [{"month":"February","price":37.85},{"month":"January","price":73.24},{"month":"February","price":61.41},
{"month":"April","price":41.07},{"month":"March","price":34.50},{"month":"April","price":68.52},
{"month":"March","price":44.53},{"month":"April","price":44.95},{"month":"January","price":72.86},
{"month":"February","price":58.96},{"month":"April","price":88.62},{"month":"April","price":32.53},
{"month":"January","price":61.02},{"month":"April","price":22.92},{"month":"April","price":79.40},
{"month":"April","price":13.23},{"month":"February","price":26.31},{"month":"February","price":74.30},
{"month":"March","price":28.76},{"month":"March","price":85.51},{"month":"March","price":75.88},
{"month":"January","price":22.83},{"month":"January","price":44.39},{"month":"February","price":22.04},
{"month":"April","price":56.89},{"month":"February","price":86.19},{"month":"April","price":87.99},
{"month":"January","price":14.25},{"month":"March","price":60.80},{"month":"February","price":23.65}]

const purchasesByMonth = _.groupBy(purchases, 'month'); 

const totalByMonth = _.map(purchasesByMonth, e => {
return _.reduce(e, function(memo, num){ 
return {month: memo.month, price: (memo.price + num.price) }
 });
})

console.log(totalByMonth)



// What are Collection functions in underscore?

    // Methods that are useable with arrays, objects and array like objects referred to as 'lists'.
  

_.map(List, Iteratee callback Function(element, index, list))
// Returns list


_.each(List, Iteratee callback Function(element, index, list))
// Returns list?

_.reduce(List, Iteratee callback Function(element, index, list), Memo) 
// Returns a single value





///// FUNCTIONAL PROGRAMMING 

// What is functional programming?

    // A style of writing code. A programming paradigm. 

    // Uses 'pure' functions.

    // Does not share state or mutate state. 



// What is a 'pure' function?

    // A pure function is a function that only cares about it's inputs and only returns an output. It does not have side-effects meaning it doesn't affect any variable or state outside of itself. And it does not rely on anything outside of itself to run meaning it always will return the same results if invoked with the same arguments.



// Why use functional programming?

    // It is predictable. You will always be getting the same results. 

    // It is testable. Because you don't share or mutate state and only rely on inputs, you should always have the same output which makes debugging and testing much smoother. 



// How do you do functional programming?

    // Use pure functions for everything. Example: instead of a for loop use .map(), .filter(), .reduce(). Basically quit your for loop habits.

    // Avoid side effects. Only return values. 

    // Treat your data as immutable. 

    // Higher order functions, closures, callbacks, etc...

    // Piecing together functions by using method chaining. let result = array.filter().map().reduce()



// Why treat data as immutable?

    // If someone else is using the same data and depending on it to be a certain way, you changing it can break all their things. You creating your own copy to change does not break their code. 



    
//// DEBUGGING 

// VS Code Debugger: How do you add a breakpoint?

    // Click and add a redd dot to the left of the line number.


//** Step over button: You can step over a breakpoint and move on. 


//** Step into button: You can step into that code and see every single thing that happens within that function.


//** Step out button: It will remove itself so you no longer see all the portions of code it was evaluating. 


// When to use VS Code Debugger?

    // Debugging your server


// Why use a debugger?

    // Much more beneficial way to debug than console.logs and much more efficient. 



//// Chrome Developer Tools: 

//** Elements Tab: When you hover over elements on your page, Blue is element, Green is padding, Orange is margin. You can trial run changes to your css. 


//** Sources Tab: Gives you all the sources from your application. You can see your files within this tab. 


// Chrome Debugger: How to get started?

    // Open your Chrome developer tools, go to 'Sources' tab. Click into the files on the left to find the one you are looking for and needing to debug. 


// How to add a breakpoint?

    // Click on the number of the line you want to add a breakpoint and a blue tag will appear. This is your breakpoint. 


// What does the Network tab do?

    // You can see all the requests made by the application and their status codes amongst other things. 

    //Preserve log will keep your list even if you refresh the page. Without doing this it will not save all the previous requests. If you disable cache it will show you what its like to be a first time visitor to your app. 


// What does the Application tab do?

    // You can see any storage associated with this website. Example: cookies. 

    // You can clear your cache and such here. 

    // A service worker is a way to cache your site. It is great for production but not so much developement. If you go to clear storage and scroll to the bottom you can click 'clear site data'. Useful when getting weird issues. 

    // You can see any registered service workers you have. 



// What does the Audit tab do?

    // It will audit your app and show you which ones you've passed or not. Progressive Web App, Preformance, Accessibility, and Best Practices. If you open the ones you've failed it will give you tips on how to pass it. Very useful information when making your app more efficient. 

