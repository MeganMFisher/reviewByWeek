// What is a closure?

  // *Function within a function (enclosed scope)
  // *Inner function is return from outer function

 



























 //A constructor is useful when you want to create multiple similar objects with the same properties and methods. It’s a convention to capitalize the name of constructors to distinguish them from regular functions.
  //
  
  
  // The last line of the code creates an instance of Book and assigns it to a variable; even though the Book constructor doesn't do anything, myBook is still an instance of it. As you can see there is no difference between this function and regular functions except that we call it with the new keyword and the function name is capitalized.
  
  // A constructor is like a cookie cutter to make more than one object with similar features. In other words, the benefit of using a constructor is that it makes it easy to create multiple objects with the same properties and methods.
  
  
  
function Book() { 
  var num = 0
  return num += 5
} 
var myBook = new Book();
Book()
