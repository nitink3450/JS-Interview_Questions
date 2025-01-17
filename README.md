# JS-Interview_Questions and Answers.

### JavaScript Interview Questions & Answers


## 1.What is JS ?
Javascript is a combination of both compiler and interpreter and it works on the concept of JIT (Just in time compilation). In this the whole code gets compiled in one single shot and then directly it goes for execution , no file gets generated.

Javascript is a -

   1.  Synchronous lanaguage means the complete code will be executed line by line
   2.  Single Threaded language means once the error occurs then the execution will stop at that line itself.
   3.  Dynamic Programming Language means when you are creating a variable and assigning it some value then this value type can be changed throughout the whole code execution which is not applicable in other programming languages.

## 2. What is JS engine and what are different engines available?
JS engine is a program which gets used to execute the JS code. All the browsers have their own JS engine. But out of all the most famous one is V8 engine provided by Google chrome. Internet Explorer has Chakra Mozilla Firefox has Spider Monkey

Every code that has to be executed firstly gets converted into machine level language which is a combination of 0 and 1. This code is understandable by machine and then it finally gets executed. Now this complete process is known as compilation and it can be done by either compiler or interpreter.

In case of compiler the complete code gets converted into machine level in a single shot and it creates a file which finally gets used in execution. whereas in case of interpreter the code gets converted into machine level line by line and it does not create any file.

## 3. What is the difference between var let and const?
In JavaScript, users can declare a variable using 3 keywords that are var, let, and const.
var keyword is oldest keyword and let and const are introduced in es6.
•	var declarations are globally scoped or function scoped while let and const are block scoped.
•	var variables can be updated and re-declared within its scope; let variables can be updated but not re-declared; const variables can neither be updated nor re-declared.
•	They are all hoisted to the top of their scope. But while var variables are initialized with undefined, let and const variables are not initialized.
•	While var and let can be declared without being initialized, const must be initialized during declaration.

## 4. what is temporal dead zone?
The Temporal Dead Zone is a behavior in JavaScript that occurs when declaring a variable with the let and const keywords, but not with var. In ECMAScript 6, accessing a let or const variable before its declaration (within its scope) causes a ReferenceError. The time span when that happens, between the creation of a variable’s binding and its declaration, is called the temporal dead zone.

Let's see this behavior with an example,

    function somemethod() {
      console.log(counter1); // undefined
      console.log(counter2); // ReferenceError
      var counter1 = 1;
      let counter2 = 2;
    }

## 5. what is hoisting ?
Hoisting is a JavaScript mechanism where variables, function declarations and classes are moved to the top of their scope before code execution. Remember that JavaScript only hoists declarations, not initialisation. Let's take a simple example of variable hoisting,

    console.log(message);    //output : undefined
    var message = "The variable Has been hoisted";

The above code looks like as below to the interpreter,

    var message;
    console.log(message);
    message = "The variable Has been hoisted";

In the same fashion, function declarations are hoisted too

    message("Good morning");    //Good morning

    function message(name) {
      console.log(name);
    }

This hoisting makes functions to be safely used in code before they are declared.

## 6. what is arrow functions ?
An arrow function is a shorter syntax for a function expression and does not have its own this, arguments, super, or new.target. These functions are best suited for non-method functions, and they cannot be used as constructors.
Arrow functions, introduced in ES6, provides a concise way to write functions in JavaScript. Another significant advantage it offers is the fact that it does not bind its own this. In other words, the context inside arrow functions is lexically or statically defined.

    user=[array of elements];
    const a=() => {
       console.log(user)
    }

## 7. What is typeOf operator?
Typeof in JavaScript is an operator used for type checking and returns the data type of the operand passed to it. The operand can be any variable, function, or object whose type you want to find out using the typeof operator.
We can use typeof in JavaScript to check the data type of the following operands:
    Number, String, Undefined, Boolean, Object, Symbol, Function

Here, we will pass numbers as operands and use the typeof operator and log the result to the console. We will use a positive integer, negative integer, zero, floating-point number, infinity, NaN, and Math equations as operands. We will also use the concept to explicitly typecasting and parsing a string to an integer or float and use it as an operand. The code below demonstrates the use of all of these operands.
    console.log(typeof 12) , console.log(typeof -31), console.log(typeof 0)  // "number"

                             (or)
You can use the JavaScript typeof operator to find the type of a JavaScript variable. It returns the type of a variable or an expression.

    typeof "John Abraham"; // Returns "string"
    typeof (1 + 2); // Returns "number"

## 8. What is the difference between == && ===?
JavaScript provides both strict(===, !==) and type-converting(==, !=) equality comparison. The strict operators take type of variable in consideration, while non-strict operators make type correction/conversion based upon values of variables. The strict operators follow the below conditions for different types,

  1. Two strings are strictly equal when they have the same sequence of characters, same length, and same characters in corresponding positions.
  2. Two numbers are strictly equal when they are numerically equal. i.e, Having the same number value. There are two special cases in this,
      i. NaN is not equal to anything, including NaN.
      ii. Positive and negative zeros are equal to one another.
  3. Two Boolean operands are strictly equal if both are true or both are false.
  4. Two objects are strictly equal if they refer to the same Object.
  5. Null and Undefined types are not equal with ===, but equal with ==. i.e, null===undefined --> false but null==undefined --> true

Some of the example which covers the above cases,

   0 == false   // true
   0 === false  // false
   1 == "1"     // true
   1 === "1"    // false
   null == undefined // true
   null === undefined // false
   '0' == false // true
   '0' === false // false
   []==[] or []===[] //false, refer different objects in memory
   {}=={} or {}==={} //false, refer different objects in memory

## 9. What is the difference between undefined and null ?
Below are the main differences between null and undefined,
Null::                   
 1. It is an assignment value which indicates that variable points to no object. 
 2. Type of null is object.
 3. The null value is a primitive value that represents the null, empty, or non-existent reference.
 4. Indicates the absence of a value for a variable.
 5. Converted to zero (0) while performing primitive operations.
 
Undefined:: 
 1. It is not an assignment value where a variable has been declared but has not yet been assigned a value.
 2. Type of undefined is undefined.
 3. The undefined value is a primitive value used when a variable has not been assigned a value.
 4. Indicates absence of variable itself.
 5. Converted to NaN while performing primitive operations.

## 10. What is Nan?
The isNaN() function is used to determine whether a value is an illegal number (Not-a-Number) or not. i.e, This function returns true if the value equates to NaN. Otherwise it returns false.Not a Number, is a member of a numeric data type that can be interpreted as a value that is undefined

   isNaN("Hello");   //true
   isNaN("100");     //false

## 11. What is Functions?
In Javascript, functions can also be defined as expressions. 
For example, 
// program to find the square of a number 
// function is declared inside the variable 
    let x = function (num) {
       return num * num 
    }; 
    console.log(x(4)); // can be used as variable value for other variables
    let y = x(3);
    console.log(y); 

## 12. What is an Anonymous Functions?
An anonymous function is a function without a name! Anonymous functions are commonly assigned to a variable name or used as a callback function.
                              (or)
Anonymous Function is a function that does not have any name associated with it. Normally we use the function keyword before the function name to define a function in JavaScript, however, in anonymous functions in JavaScript, we use only the function keyword without the function name.
An anonymous function is not accessible after its initial creation, it can only be accessed by a variable it is stored in as a function as a value. An anonymous function can also have multiple arguments, but only one expression.

The syntax would be as below,

    function (optionalParameters) {
      //do something
    }
    
    const myFunction = function(){ //Anonymous function assigned to a variable
      //do something
    };
    
    [1, 2, 3].map(function(element){ //Anonymous function used as a callback function
      //do something
    });

## 13. What is IIFE?
IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined. The signature of it would be as below,

    (function () {
      // logic here
    })();

The primary reason to use an IIFE is to obtain data privacy because any variables declared within the IIFE cannot be accessed by the outside world. i.e, If you try to access variables with IIFE then it throws an error as below,

    (function () {
      var message = "IIFE";
        console.log(message);
    })();
    console.log(message); //Error: message is not defined

## 14. What are High Order Functions?
Higher-order function is a function that accepts another function as an argument or returns a function as a return value or both.

    const firstOrderFunc = () =>
      console.log("Hello, I am a First order function");
    const higherOrder = (ReturnFirstOrderFunc) => ReturnFirstOrderFunc();
    higherOrder(firstOrderFunc);
## 15. What is First Class Functions?
In Javascript, functions are first class objects. First-class functions means when functions in that language are treated like any other variable.

For example, in such a language, a function can be passed as an argument to other functions, can be returned by another function and can be assigned as a value to a variable. For example, in the below example, handler functions assigned to a listener

    const handler = () => console.log("This is a click handler function");
    document.addEventListener("click", handler);

## 16. What is Function Expressions?
Function Expression allows us to create an anonymous function which doesn't have any function name which is the main difference between Function Expression and Function Declaration. A function expression can be used as an IIFE (Immediately Invoked Function Expression)which runs as soon as it is defined. A function expression has to be stored in a variable and can be accessed using variableName.  With the ES6 features introducing Arrow Function, it becomes more easier to declare function expression.

## 17. What is a Pure Functions ?
A Pure function is a function where the return value is only determined by its arguments without any side effects. i.e, If you call a function with the same arguments 'n' number of times and 'n' number of places in the application then it will always return the same value.

Let's take an example to see the difference between pure and impure functions,


    //Impure
    let numberArray = [];
    const impureAddNumber = (number) => numberArray.push(number);
    //Pure
    const pureAddNumber = (number) => (argNumberArray) =>
      argNumberArray.concat([number]);
    
    //Display the results
    console.log(impureAddNumber(6)); // returns 1
    console.log(numberArray); // returns [6]
    console.log(pureAddNumber(7)(numberArray)); // returns [6, 7]
    console.log(numberArray); // returns [6]

As per the above code snippets, the Push function is impure itself by altering the array and returning a push number index independent of the parameter value. . Whereas Concat on the other hand takes the array and concatenates it with the other array producing a whole new array without side effects. Also, the return value is a concatenation of the previous array.

Remember that Pure functions are important as they simplify unit testing without any side effects and no need for dependency injection. They also avoid tight coupling and make it harder to break your application by not having any side effects. These principles are coming together with Immutability concept of ES6 by giving preference to const over let usage.
                                   (or)
A Pure Function is a function (a block of code) that always returns the same result if the same arguments are passed. It does not depend on any state or data change during a program’s execution. Rather, it only depends on its input arguments.When a same input is passed every time the function will return same output.

    function calculate(sum){         // 2
       return (sum+ 0.5);           // 2.5
    }
    calculate(2);    //2.5      
    calculate(5);    //5.5

## 18. What is Callback Functions ?
A callback function is a function passed into another function as an argument. This function is invoked inside the outer function to complete an action. Let's take a simple example of how to use callback function

    function callbackFunction(name) {
      console.log("Hello " + name);
    }
    
    function outerFunction(callback) {
      let name = prompt("Please enter your name.");
      callback(name);
    }
    
    outerFunction(callbackFunction);

## 19. What is the generator function?
ES6 introduced a new way of working with functions and iterators in the form of Generators (or generator functions). A generator is a function that can stop midway and then continue from where it stopped. In short, a generator appears to be a function but it behaves like an iterator.

A generator is a function that can stop midway and then continue from where it stopped.
Here are some other common definitions of generators —
  1. Generators are a special class of functions that simplify the task of writing iterators.
  2. A generator is a function that produces a sequence of results instead of a single value, i.e you generate ​a series of values.
In JavaScript, a generator is a function which returns an object on which you can call next(). Every invocation of next() will return an object of shape.

Let’s see how we can create a generator in JavaScript —

    function * generatorFunction() { // Line 1
      console.log('This will be executed first.');
      yield 'Hello, ';   // Line 2
      console.log('I will be printed after the pause');  
      yield 'World!';
    }
    const generatorObject = generatorFunction(); // Line 3
    console.log(generatorObject.next().value); // Line 4
    console.log(generatorObject.next().value); // Line 5
    console.log(generatorObject.next().value); // Line 6
  Output::
    // This will be executed first.
    // Hello, 
    // I will be printed after the pause
    // World!
    // undefined

## 20. What are operators?
An operator is capable of manipulating(mathematical and logical computations) a certain value or operand. There are various operators supported by JavaScript as below,

  1. Arithmetic Operators: Includes + (Addition),– (Subtraction), * (Multiplication), / (Division), % (Modulus), + + (Increment) and – – (Decrement)
  2. Comparison Operators: Includes = =(Equal),!= (Not Equal), ===(Equal with type), > (Greater than),> = (Greater than or Equal to),< (Less than),<= (Less than or Equal to)
  3. Logical Operators: Includes &&(Logical AND),||(Logical OR),!(Logical NOT)
  4. Assignment Operators: Includes = (Assignment Operator), += (Add and Assignment Operator), – = (Subtract and Assignment Operator), *= (Multiply and Assignment), /= (Divide and Assignment), %= (Modules and Assignment)
  5. Ternary Operators: It includes conditional(: ?) Operator
  6. typeof Operator: It uses to find type of variable. The syntax looks like typeof variable.

## 21. What is closure in javascript?
A closure is the combination of a function and the lexical environment within which that function was declared. i.e, It is an inner function that has access to the outer or enclosing function’s variables. The closure has three scope chains.
  i. Own scope where variables defined between its curly brackets
  ii. Outer function’s variables
  iii. Global variables.

Let's take an example of closure concept,

    function Welcome(name) {
      var greetingInfo = function (message) {
        console.log(message + " " + name);
      };
      return greetingInfo;
    }
    var myFunction = Welcome("John");
    myFunction("Welcome "); //Output: Welcome John
    myFunction("Hello Mr."); //output: Hello Mr.John

As per the above code, the inner function(i.e, greetingInfo) has access to the variables in the outer function scope(i.e, Welcome) even after the outer function has returned.

## 22. what is function currying with example ?
Currying is the process of taking a function with multiple arguments and turning it into a sequence of functions each with only a single argument. Currying is named after a mathematician Haskell Curry. By applying currying, a n-ary function turns it into a unary function.

Let's take an example of n-ary function and how it turns into a currying function,

    const multiArgFunction = (a, b, c) => a + b + c;
    console.log(multiArgFunction(1, 2, 3)); // 6
    
    const curryUnaryFunction = (a) => (b) => (c) => a + b + c;
    curryUnaryFunction(1); // returns a function: b => c =>  1 + b + c
    curryUnaryFunction(1)(2); // returns a function: c => 3 + c
    curryUnaryFunction(1)(2)(3); // returns the number 6

Curried functions are great to improve code reusability and functional composition.

## 23. Write a function to delete a character from any string?
Using Substring Method:
    function removeFirstCharacter() {
    var str = 'tracedynamics';
    str = str.substring(1);
    console.log(str); 
    }
    removeFirstCharacter();  //racedynamics
Using Slice Method:
    function removeFirstCharacter() {
    var str = 'tracedynamics';
    str = str.slice(1);
    console.log(str); 
    }
    removeFirstCharacter()   //racedynamics
Using replace method:
    function replaceFirstCharacter() {
    var str = 'tracedynamics';
    str = str.replace('t','T');
    console.log(str); 
    }
    replaceFirstCharacter()   //Tracedynamics

## 24. Define Weakset, Weakmap.
Weakset::
WeakSet is used to store a collection of weakly(weak references) held objects. The syntax would be as follows,
    new WeakSet([iterable]);
Let's see the below example to explain it's behavior,
    var ws = new WeakSet();
    var user = {};
    ws.add(user);
    ws.has(user); // true
    ws.delete(user); // removes user from the set
    ws.has(user); // false, user has been removed

Weakmap::
The WeakMap object is a collection of key/value pairs in which the keys are weakly referenced. In this case, keys must be objects and the values can be arbitrary values. The syntax is looking like as below,
    new WeakMap([iterable]);
Let's see the below example to explain it's behavior,
    var ws = new WeakMap();
    var user = {};
    ws.set(user);
    ws.has(user); // true
    ws.delete(user); // removes user from the map
    ws.has(user); // false, user has been removed

## 25. What is the difference bw Map and forEach?
The main difference between map and forEach is that the map method returns a new array by applying the callback function on each element of an array, while the forEach method doesn't return anything,its updates the same array. You can use the forEach method to mutate the source array, but this isn't really the way it's meant to be used.
Let's see the below example to explain it's behavior,

    var salary = [100,200,300,400,500];

    console.log('Before Salary',salary);
    const newArr = salary.map(x => x+200);

    const neweach= salary.forEach((x) =>{if(x > 400){return (x + 10);}});
    console.log("After Salary",neweach);

## 26. What is the difference between filter and find?
 1.	.find() will look and stop after the first match, whereas, .filter() will continue searching through the entire array.
 2.	filter reduces the set of already matched elements, while find gets descendants of the matched element.
 3.	Both filter() and find() methods are very similar, except the former is applies to all the elements, while latter searches child elements only.
    filter() – search through all the elements.        find() – search through all the child elements only.

var folks = [ 
    {name: "Bob", age: "32", occupation: "developer"}, 
    {name: "Bill", age: "17", occupation: "delinquent"}, 
    {name: "Brad", age: "40", occupation: "yes"} 
  ]

let resu = folks.find( x => x.name === "Bob");
console.log(resu);
//Returns an object: {name: "Bob", age: "32", occupation: "developer"}

let result = folks.filter( y => y.name === "Bob");
console.log(result);
//Returns an array: [ {name: "Bob", age: "32", occupation: "developer"} ]

## 27. What is Prototype and Prototype Chaining?
Prototype:: An object's prototype ,object may also have a prototype object, which it inherits methods and properties from, and so on. This is often referred to as a prototype chain, and explains why different objects have properties and methods defined on other objects available to them.
    function Person(first, last, age, eyecolor) {
      this.firstName = first;
      this.lastName = last;
      this.age = age;
      this.eyeColor = eyecolor;
    }

    const myFather = new Person("John", "Doe", 50, "blue");
    const myMother = new Person("Sally", "Rally", 48, "green");
    console.log(myFather);
    console.log(myMother);

//in case, if you want to add other properties in the object created using function constructor.

    myFather.age = 49;
    console.log(myFather);

//in case when you want to add properties inside the function constructor.

    Person.prototype.City = "Vizag";
    myFather.City = "Vijaywada";
    console.log(myFather.City);

Prototype chaining:: It is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language.

The prototype on object instance is available through Object.getPrototypeOf(object) or **proto** property whereas prototype on constructors function is available through Object.prototype.

<img src="./Images/prototype_chain.png"alt ="Prototype Chain png">

## 28. What is Call apply bind method?
call():  it is use for calling the fun , we need to give comma separated..,in case of call, each and every arguments which is required to be passed to the function will be passes individually.
    displayUserDetails.call(user, "TCS", "developer").
    displayUserDetails(user);
Apply() : each and every arguments which is required to be passed to the function will be inside an array.
    displayUserDetails.apply(user, ["TCS", "developer"]).
bind(): it will return you new function, and this new function , we can call at anytime and anywhere.
    const newFun = displayUserDetails.bind(user);
    newFun("Infosys", "Tester")

## 29. window object v/s document object 
# Document Object:
 The document object represent a web page that is loaded in the browser. By accessing the document object, we can access the element in the HTML page. With the help of document objects, we can add dynamic content to our web page. The document object can be accessed with a window.document or just document.
  Syntax:
    document.property_name;   (body, domain, URL, head, ….)
  Syntax:
    window.method_name;   (createElement, getElementById, …)
# Window Object: 
The window object is the topmost object of the DOM hierarchy. It represents a browser window or frame that displays the contents of the webpage. Whenever a window appears on the screen to display the contents of the document, the window object is created. 
  Syntax:
    window.property_name;   (console, document…)	
  Syntax:
    window.method_name;   (alert, setTimeout,setInterval….)

## 30.Difference between Splice and slice.
some of the major difference in a tabular form

             Slice                                                         Splice
Doesn't modify the original array(immutable)	                 Modifies the original array(mutable)
Returns the subset of original array	                         Returns the deleted elements as array
Used to pick the elements from array                         	 Used to insert or delete elements to/from array

## 31. What is Global Execution Conext?
The global execution context is the default or first execution context that is created by the JavaScript engine before any code is executed(i.e, when the file first loads in the browser). All the global code that is not inside a function or object will be executed inside this global execution context. Since JS engine is single threaded there will be only one global environment and there will be only one global execution context.

For example, the below code other than code inside any function or object is executed inside the global execution context.

     var x = 10;
     function A() {
       console.log("Start function A");
       function B() {
         console.log("In function B");
       }
       B();
     }
     A();
     console.log("GlobalContext");

## 32. What are callbacks and why do we use it?
A callback function is a function passed into another function as an argument. This function is invoked inside the outer function to complete an action. Let's take a simple example of how to use callback function

     function callbackFunction(name) {
       console.log("Hello " + name);
     }
     function outerFunction(callback) {
       let name = prompt("Please enter your name.");
       callback(name);
     }
     outerFunction(callbackFunction);

# Why do we need callbacks:::
The callbacks are needed because javascript is an event driven language. That means instead of waiting for a response javascript will keep executing while listening for other events. Let's take an example with the first function invoking an API call(simulated by setTimeout) and the next function which logs the message.

      function firstFunction() {
        // Simulate a code delay
        setTimeout(function () {
          console.log("First function called");
        }, 1000);
      }
      function secondFunction() {
        console.log("Second function called");
      }
      firstFunction();
      secondFunction();

Output;
    // Second function called
    // First function called
As observed from the output, javascript didn't wait for the response of the first function and the remaining code block got executed. So callbacks are used in a way to make sure that certain code doesn’t execute until the other code finishes execution.

## 33. What are the different types of errors in javascript?
There are 6 different types of error names returned from error object,

EvalError	     =  An error has occurred in the eval() function
RangeError     =	An error has occurred with a number "out of range"
ReferenceError =	An error due to an illegal reference
SyntaxError	   =  An error due to a syntax error
TypeError      =	An error due to a type error
URIError       =	An error due to encodeURI()

for details: go through blog:
https://blog.bitsrc.io/types-of-native-errors-in-javascript-you-must-know-b8238d40e492

## 34. "Load time error  , Run time error "
# Load time error::
Load-time errors are those that are caught by JavaScript as Navigator loads the script. These errors are the major mistakes that prevent the script from functioning before it has a chance to start.
# Run time error:: 
Runtime errors, also called exceptions, occur during execution (after compilation/interpretation). For example, the following line causes a runtime error because here the syntax is correct, but at runtime, it is trying to call a method that does not exist.

## 35. Can you explain why we use async-await?
await can be used on its own with JavaScript modules. Note: The purpose of async / await is to simplify the syntax necessary to consume promise-based APIs. The behavior of async / await is similar to combining generators and promises. Async functions always return a promise.
To avoid of multiple .then blocks(promise chaining) by using async/await.

## 36. What are Promises and why do we need them?
A promise is an object that may produce a single value some time in the future with either a resolved value or a reason that it’s not resolved(for example, network error). It will be in one of the 3 possible states: fulfilled, rejected, or pending.

The syntax of Promise creation looks like below,

    const promise = new Promise(function (resolve, reject) {
      // promise description
    });

The usage of a promise would be as below,

    const promise = new Promise(
      (resolve) => {
        setTimeout(() => {
          resolve("I'm a Promise!");
        }, 5000);
      },
      (reject) => {}
    );

    promise.then((value) => console.log(value));

The action flow of a promise will be as below,
<img src="./Images/promises.png" alt="promises">

# why do we need them::
Promises are used to handle asynchronous operations. They provide an alternative approach for callbacks by reducing the callback hell and writing the cleaner code.

## 37. Difference between ES5 and ES6.
# ES5::
1.	ECMA script is a trademarked scripting language specification defined by Ecma international. The fifth edition of the  same is known as ES5.
2.	It was introduced in 2009.	
3.	It supports primitive data types that are string, number, boolean, null, and undefined.
4.	There are only one way to define the variables by using the var keyword.	
5.	It has a lower performance as compared to ES6.
6.	Object manipulation is time-consuming in ES5.	
7.	In ES5, both function and return keywords are used to define a function.	
8.	It provides a larger range of community supports than that of ES6. 

# ES6::
1.	ECMA script is a trademarked scripting language specification defined by Ecma international. The sixth edition of the same is known as ES6.
2.  It was introduced in 2015.
3.  In ES6, there are some additions to JavaScript data types. It introduced a new primitive data type ‘symbol’ for supporting unique values.
4.  There are two new ways to define variables that are let and const.
5.  It has a higher performance than ES5.
6.  Object manipulation is less time-consuming in ES6.
7.  An arrow function is a new feature introduced in ES6 by which we don’t require the function keyword to define the function.
8.  It provides a less range of community supports than that of ES5.

## 38. Explain the difference setTimeout and setInterval function and write its syntax.
# setTimeout::
The setTimeout() method is used to call a function or evaluate an expression after a specified number of milliseconds. For example, let's log a message after 2 seconds using setTimeout method,

    setTimeout(function () {
      console.log("Good morning");
    }, 2000);
# setInterval::
The setInterval() method is used to call a function or evaluate an expression at specified intervals (in milliseconds). For example, let's log a message after 2 seconds using setInterval method,

    setInterval(function () {
      console.log("Good morning");
    }, 2000);

## 39. Explain call back hell.
Callback Hell is an anti-pattern with multiple nested callbacks which makes code hard to read and debug when dealing with asynchronous logic. The callback hell looks like below,

    async1(function(){
        async2(function(){
            async3(function(){
                async4(function(){
                    ....
                });
            });
        });
    });

## 40. What is an Event loop?
The Event Loop is a queue of callback functions. When an async function executes, the callback function is pushed into the queue. The JavaScript engine doesn't start processing the event loop until the async function has finished executing the code. Note: It allows Node.js to perform non-blocking I/O operations even though JavaScript is single-threaded.







 

Good luck with your interview 😊
