# Programming Introduction
* For simple tasks, you can use existing applications.
* A program is a set of detailed instructions telling a computer what to do.
* The art of programming is controlling and managing complexity.
* When action grows unprofitable, gather information; when information grows unprofitable, sleep.

## Computing Basics
* All information in computers is represented as sequences of bits.
* Bits are two-valued things (1 and 0) OR (shiny dot on CD and dull dot on CD).
* Two types of data storage
  * Volatile = working memory = RAM
  * Non-volatile = permanent storage = hard drive

## Javascript Basics
  * JS is a weakly typed language (don't have to declare data types)
    * Can lead to odd type conversions
  * ECMA2015 (ES6)
  * **Variables/Bindings** are a form of temporary storage. The data they contain disappears when a user navigates away from the web page, unless you transfer them to more permanent storage.
  * A code fragment that produces a **value** is called an **expression**.
  * **Statements** are the sentences of code. In JavaScript, they end with a semicolon.

## Bits, Values, and Data types
* Chunks of bits are called **values**
  * JavaScript uses 64 bits per value for numbers and 16 bits per value for strings
* Values can be separated into **data types**
  * booleans: ```true``` and ```false```
  * strings: ``` `String`, 'String', or "String" ```
    * template literals: ``` `String in backticks with ${code}` ```
  * numbers: integers ```7``` and floats ```7.81``` and scientific ```7.1e8```
    * 3 special numbers: Infinity, -Infinity, NaN
* Converting between data types
  * String to integer: ```parseInt(string)```
  * String to floating-point: ```parseFloat("string")```
  * Check if a string contains any numbers by using ```isNaN()``` Returns true or false

## Operators
* Comparison Operators
  * ```> , < , >= , <= , == , != , ===```
* Logical Operators
  * ```&& , || , !```
* Arithmetic Operators
  * ```+ , - , * , / , %, **``` The exponential operator was added in 2016 (ES7)
* Unary Operators
  * ``` typeof ``` and ``` - ```
* Conditional/Ternary Operator
  * ``` true ? iftrue : iffalse ```

## Data Structures
  * arrays ```let arrayVar = [val1,val2,val3];```
  * objects
  * lists
  ```
  let list = { value: 1, rest: {
    value: 2, rest: { value: 3, rest: null } }
  };
  ```
  * Maps and Sets

---

# JavaScript Functions
  * Parameters are variables that act as placeholders for the values that are to be input to a function when it is called. When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or "passed") into a function when it is called are known as arguments.
  * Return statements work similar to break statements... they exit the function
  * You execute a function by *calling* or *invoking* the function
  * Variables created within a function only have local scope and disappear after the function ends
  * *Side effects* are changes a function makes outside of itself
  * Default parameters were introduced in ES6

  ```
  function fxnName (parameters, parameter2 = defaultValue){
    // JS statements;
    return thingToBeReturned;
  }
  ```
  OR
  ```
  const fxnName = function(...args) { // ...args is called the REST parameters and feeds all args into an array called args. Intrudeced by ES6
    JS statements;
    return thingToBeReturned;
  };
  ```
  OR
  ```
  const power = (base, exponent) => { //curly braces allow for mutli-line function
    let result = 1;
    for (let count = 0; count < exponent; count++) {
      result *= base;
    }
    return result;
  };
  ```

## How Functions work
* Referencing a specific instance of a local binding in an enclosing scope—is called closure. A function that references bindings from local scopes around it is called a closure. This behavior not only frees you from having to worry about lifetimes of bindings but also makes it possible to use function values in some creative ways.
* The **call stack** is a data structure where a computer stores the context in which a function was called, this way it knows where to resume execution after the function finishes
* **Recursion** is when a function calls itself. Generally, multiple function calls is more costly than simple loops, which leads to a balance of human-friendliness vs machine-friendliness.

## Higher-Order Functions
  * Functions that operate on other functions, either by taking them as arguments or by returning them, are called higher-order functions.
  * This allow us to abstract over actions, not just values.
  * One area where higher-order functions shine is data processing.

## Functions as Object properties
* Each function has its own this binding, whose value depends on the way it is called, you cannot refer to the this of the wrapping scope in a regular function defined with the function keyword.
* Arrow functions are different—they do not bind their own this but can see the this binding of the scope around them. Thus, you can do something like the following code, which references this from inside a local function.
* To explicitly call a function instead of using it as a method, you can use fxnName.call(objectCalled, otherParam) instead of objectCalled.fxnName(otherParam);

---

# Flow Control

## If Statements
```
if (x == "value1") action1();
else if (x == "value2") action2();
else if (x == "value3") action3();
else defaultAction();
```

## Switch statements
```
switch (test expression){
  case (possibility1):
    // JS statements;
    break;
  case (possibility2):
  case (possibility3):
    // JS statements; // will be executed both for possibility2 and possibility3
    break;
  default:
    // default JS statements;
    break;
}
```

## Loop Breaks and Continues
* Break statements exits a loop prematurely
* Continue statements end the current loop and returns to the beginning of the loop
  * Starts execution of the loop of the next iteration

## For Loops
* Basic for loop
```
for ([initialization]; [condition]; [final-expression]){
  JavaScript statements;
};
```
* For Of Loop
  * For each in is deprecated; use the For/Of loop instead
```
for (variable of iterable) {
  statement
}
```

## While Loops
* Traditional while loop (possible to never execute):
```
while(i < 5){ ourArray.push(i); i++; }
```
* Do...while loop (always executes at least once)
```
do{ userAge = prompt(“Please enter your age”,””); }
while (isNaN(userAge) == true);
```

---

# Objects
* JavaScript **objects** are very similar to Python *dictionaries*
* You can nest objects within objects
  * These are accessed by dot chaining ```myObj.nestedObj.property```
* A JavaScript object is one way to handle flexible data. They allow for arbitrary combinations of strings, numbers, booleans, arrays, functions, and objects.
* Objects are arbitrary collections of properties.
  * Properties whose names aren’t valid binding names or valid numbers have to be quoted.
  * **Methods** are simply properties that hold function values.
    * A special binding called **this** automatically points at the object the method was called from

## Encapsulation
* The core idea in object-oriented programming is to divide programs into smaller pieces and make each piece responsible for managing its own state.
* Different encapsulated pieces interact with each other through **interfaces**: limited sets of functions and bindings that provide some functionality while hiding their implementation.
* Many programming langauges allow you to make certain features of an object private or public... JS does not.
  * Instead, parts are kept private by omiting from documentaiton and/or starting the binding with an underscore.

## Creating a new object
```
var objectName = {
  "property": value,
  "property": "value",
  "property3": ["array","of","strings"]
};
```

## JavaScript Object Notation (JSON)
* JSON are a subset of JavaScript Objects that must follow this notation:
let JSONobj = {
  {
  "prop","val",
  "prop","val"
  },
  {
  "prop","val",
  "prop","val"
  }
}

## Object constructors
* Creating a variable inside a constructor makes it a private variable
* To modify private variables, you need methods, which are created by:
```
var ObjectName = function(){
  var hiddenVariable; // private variable

  this.getVar = function(){
    return hiddenVariable;
  }
}
```
* Constructor functions are given capitalized names to make it clear that they are constructors
```
var Car = function(param1, param2, param3) {
  this.wheels = param1; // creates a new property of Car called wheels with a value of 4
  this.engines = param2;
  this.seats = param3;
};
```
* Using a constructor to make an instance of an object
```
var myNewCar = new Car();
```

function speak(line) {
  console.log(`The ${this.type} rabbit says '${line}'`);
}
let whiteRabbit = {type: "white", speak};
let hungryRabbit = {type: "hungry", speak};

## Object methods
* Check if object has a specific property
```
objectName.hasOwnProperty();
OR
"property" in objectName;
```

* Obtain the value of a property using the dot operator
```
objectName.property;
```

* Obtain the value of a property using brackets. Must be used if spaces in prop name
```
objectName["property name"]
```

* Update the value of a property in an object at any time using the assignment operator
In a similar fashion, adding a new property is done by...
```
objectName.newProperty = initial value;
```

* Delete a property from an object
```
delete ourDog.bark;
```

Both value.x and value[x] access a property on value—but not necessarily the same property. The difference is in how x is interpreted. When using a dot, the word after the dot is the literal name of the property. When using square brackets, the expression between the brackets is evaluated to get the property name. Whereas value.x fetches the property of value named “x”, value[x] tries to evaluate the expression x and uses the result, converted to a string, as the property name.

So if you know that the property you are interested in is called color, you say value.color. If you want to extract the property named by the value held in the binding i, you say value[i]. Property names are strings. They can be any string, but the dot notation works only with names that look like valid binding names. So if you want to access a property named 2 or John Doe, you must use square brackets: value[2] or value["John Doe"].

Properties that contain functions are generally called methods of the value they belong to, as in “toUpperCase is a method of a string”.

## Prototypes
* Most objects have a prototype, which is used as a fallback source of properties. If an object gets a request for a property it does not have, its prottype will be searched, then its proto's proto and so on...

Object.freeze to prevent data mutation.

Once the object is frozen, you can no longer add, update, or delete properties from it. Any attempt at changing the object will be rejected without an error

---

# Fixing errors
* The process of finding and fixing mistakes is called **debugging**
* Adding the statement ```"use strict";``` to the top of a file or function makes JS a little stricter
  * This rarely hurts and can sometimes help you spot problems
* There is a JS dialect called **TypeScript** that adds in support for types
* **Test Suites** help you build and run series of tests

These issues generally come in three forms:

syntax errors that prevent a program from running
runtime errors when code fails to execute or has unexpected behavior
semantic (or logical) errors when code doesn't do what it's meant to.

## Exceptions
Exceptions are a mechanism that makes it possible for code that runs into a problem to raise (or throw) an exception. An exception can be any value. Raising one somewhat resembles a super-charged return from a function: it jumps out of not just the current function but also its callers, all the way down to the first call that started the current execution. This is called unwinding the stack. you can set “obstacles” along the stack to catch the exception as it is zooming down. Once you’ve caught an exception, you can do something with it to address the problem and then continue to run the program.

### Common coding errors
    * Incorrect case usage, either in function/method calls or variable use
    * Incorrect number of closing parentheses or brackets
    * Confusing assignment operator (=) and equals to operator (==)
    * Confusing methods and properties
    ```
    method calls: objectName.methodName(); // uses parentheses
    property calls: objectName.property; // no parentheses
    ```

# Error Prevention and Handling
* Always validate data formats, especially for user input
* Use the Try...Catch statements
```
try {
  // Block of code to try;
} catch(exceptionObject) {
  alert(“The error is “ + exceptionObject.message);
}
```
* The code included in parentheses right after the catch statement ```exceptionObject``` is simply a variable name.
  * This variable will store an *object*, of type Error, containing information about any exception thrown during code execution inside the try code block.
  * Although different browsers have slightly different exception objects, they all support the name and message properties ```exceptionObject.name``` and ```exceptionObject.message```
* Try blocks cannot handle syntax errors.
* Use *throw* to generate your own error messages
```
throw “This is my error message”;
```
* The type of data contained in exception will depend on how the error was thrown. If it was thrown
by the browser and not by your code, exception will be an object, the exception object. If it’s thrown by
your code, then in this instance you’ve thrown only primitive strings. So the fi rst thing you need to do
is decide what type of data exception contains. If it’s a string, you know it was thrown by your code
and can deal with it accordingly. If it’s an object, and given that you know none of your code throws

# Javascript and HTML Interactions

* Loading Javascript into a HTML web page
```
<script type=”text/javascript” src=”MyCommonFunctions.js”></script>
```

* Accessing HTML document parts
```
document.getElementByID("idName");
```

* Display an alert to users
```
alert(message or data to display);
```

* Getting user input
```
var myName = prompt("Please enter your name", " ");
```

## JSON
JavaScript gives us functions, JSON.stringify and JSON.parse, that convert data to and from this format. The first takes a JavaScript value and returns a JSON-encoded string. The second takes such a string and converts it to the value it encodes.


# Built-in JavaScript Objects
### Math Object
* Generate value between 0 and 1: ```Math.random()```
* Round to nearest integer: ```Math.round()```
* Round **down** to nearest integer: ```Math.floor()```
* Round **up** to nearest integer: ```Math.ceil()```
* Calculate absolute value: ```Math.abs()```
* Constant value of Pi: ```Math.PI```

# Working With Strings and Regular Expressions
* The whitespace characters are " " (space), \r (the carriage return), \n (newline), \t (tab), and \f (the form feed).

Regular expressions allow you to find words in a string
    var expressionName = /the/gi
    inside of the slashes is the word to look for... the g means global the i means ignore case
    To select whitespace chars as the reg expression use /\s+/g
    One such selector is the digit selector \d which is used to retrieve one digit (e.g. numbers 0 to 9) in a string.

Finding digits 0-9 in a regular expression --  /\d/g.

Appending a plus sign (+) after the selector, e.g. /\d+/g, allows this regular expression to match one or more digits.

You can invert any match by using the uppercase version of the regular expression selector.
    ex. \S\gi selects the non-whitespace chars

To find the regular expressions, use match
  myString.match(regExpression)

  ["A", "B"].forEach(l => console.log(l));

# Packages and Modules
Having quality packages available for download is extremely valuable. It means that we can often avoid reinventing a program that 100 people have written before and get a solid, well-tested implementation at the press of a few keys.



# Array Properties and Methods
* Map method
  * The map method will iterate through every element of the array, creating a new array with values that have been modified by the callback function, and return it.
  * Note that it does not modify the original array.
  * Our callback can also include arguments for the index and array being acted on.
```
function map(array, transform) {
  let mapped = [];
  for (let element of array) {
    mapped.push(transform(element));
  }
  return mapped;
}
```
* Reduce method
  * The array method reduce is used to iterate through an array and condense it into one value.
  * If your array contains at least one element, you are allowed to leave off the start argument. The method will take the first element of the array as its start value and start reducing at the second element.
  * Essentially applies a function to an entire array, keeping track of values along the way.

  Our callback function can take four arguments. You will recognize three of the arguments from the map() and filter() methods. The new argument is the accumulator.
accumulator — the accumulator accumulates all of the callbacks returned values.
val — the current value being processed
index — the current index of the value being processed
arr — the original array
```
let result = arr.reduce(callback);
```
* Filter method
  * Used to iterate through an array and filter out elements where a given condition is not true.
```
function filter(array, test) {
  let passed = [];
  for (let element of array) {
    if (test(element)) {
      passed.push(element);
    }
  }
  return passed;
}
```
filter is passed a callback function which takes the current value (we've called that val) as an argument.

Any array element for which the callback returns true will be kept and elements that return false will be filtered out.

You can use the method sort to easily sort the values in an array alphabetically or numerically.


# Efficiency
A program that processes an array is most elegantly expressed as a sequence of cleanly separated steps that each do something with the array and produce a new array. But building up all those intermediate arrays is somewhat expensive.

Likewise, passing a function to forEach and letting that method handle the array iteration for us is convenient and easy to read. But function calls in JavaScript are costly compared to simple loop bodies.

Fortunately, most computers are insanely fast. If you are processing a modest set of data or doing something that has to happen only on a human time scale (say, every time the user clicks a button), then it does not matter whether you wrote a pretty solution that takes half a millisecond or a super-optimized solution that takes a tenth of a millisecond.




Unlike the previous array methods we have been looking at, sort actually alters the array in place. However, it also returns this sorted array.

sort can be passed a compare function as a callback. The compare function should return a negative number if a should be before b, a positive number if a should be after b, or 0 if they are equal.

If no compare (callback) function is passed in, it will convert the values to strings and sort alphabetically.

You can use the reverse method to reverse the elements of an array.

reverse is another array method that alters the array in place, but it also returns the reversed array.


We can use the join method to join each element of an array into a string separated by whatever delimiter you provide as an argument.

The following is an example of using join to join all of the elements of an array into a string with all the elements separated by word and:


The trim method removes whitespace (spaces, newlines, tabs, and similar characters) from the start and end of a string.

You can split a string on every occurrence of another string with split and join it again with join.

let sentence = "Secretarybirds specialize in stomping";
let words = sentence.split(" ");
console.log(words);
// → ["Secretarybirds", "specialize", "in", "stomping"]
console.log(words.join(". "));
// → Secretarybirds. specialize. in. stomping

* Rest parameter ```(...Array)```

This is a two-dimensional array, also known as a matrix. Data sets are usually distributed in the form of matrices, and NumPy makes it extremely easy to read in and work with matrices.

read in datasets using the numpy.genfromtxt() function.

import numpy
nfl = numpy.genfromtxt("nfl.csv", delimiter=",")

NumPy arrays are represented using the numpy.ndarray class

We can directly construct arrays from lists using the numpy.array() function.
The numpy.array() function can take a list or list of lists as input.
or matrices, the shape property contains a tuple with 2 elements.
matrix = numpy.array([[5, 10, 15], [20, 25, 30]])
print(matrix.shape)
The above code will result in the tuple (2,3) indicating that matrix has 2rows and 3 columns.

check data type -- numbers.dtype

int -- Integer values. An example is 10. Can be int16, int32, or int64. The suffix 16, 32, or 64 indicates how long the number can be, in bits (there are 8 bits in a byte; we'll dive more into bits and bytes later on). The higher the suffix, the larger the integers can be.
float -- Floating point values. An example is 10.6. Can be float16, float32, or float64. The suffix 16, 32, or 64 indicates how many numbers after the decimal point the number can have. The larger the suffix, the more precise the float can be.



Specifying the keyword argument dtype when reading in world_alcohol.csv, and setting it to "U75". This specifies that we want to read in each value as a 75 byte unicode data type. We'll dive more into unicode and bytes later on, but for now, it's enough to know that this will read in our data properly.
Specifying the keyword argument skip_header, and setting it to 1. This will skip the first row of world_alcohol.csv when reading in the data.




Both python and javascript are zero-based-indexing
JS = aray of arrays ---- Python = list of lists
JS = .push()        ---- Python = .append()
JS = .pop() removes last entry of an array
JS = .shift() removes the first entry of an array
JS = .unshift() adds  element to beginning (similar to push())

JS = function fxnName(args){logic};  ---- Python = def fxnName(args): logic
JS = console.log();                  ---- Python = print()

JS = true and false ---- Python = True and False
JS = && , ||        ---- Python = and , or
JS = else if        ---- Python = elif

Both JS and Python use: == , != , > , < , >= , <=
But, JS also has === and !== as strict comparisons, which do not convert data types


In the context of programming, these kinds of vocabularies are usually called abstractions. Abstractions hide details and give us the ability to talk about problems at a higher (or more abstract) level.




In Computer Science a queue is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue.



Strict equality (===) is the counterpart to the equality operator (==). Unlike the equality operator, strict equality tests both the data type and value of the compared elements



Falsy values in JavaScript are false, null, 0, "", undefined, and NaN.

# Recommended resources
* https://eloquentjavascript.net


I prefer to look at the issue from a practical, rather than ideological, angle. There are several useful concepts, most importantly that of encapsulation (distinguishing between internal complexity and external interface), that the object-oriented culture has popularized. These are worth studying.

Methods are simply properties that hold function values. This is a simple method:

JSONP (which stands for JSON with Padding) - how to get around cross-browser-origin security issue

It does this by having the server return JSON data wrapped in a function call (the “padding”) which can then be interpreted by the browser. This function must be defined in the page evaluating the JSONP response.


Both Chrome and Firefox have excellent JavaScript consoles, also known as DevTools, for debugging your JavaScript.

You can find Developer tools in your Chrome's menu or Web Console in Firefox's menu. If you're using a different browser, or a mobile phone, we strongly recommend switching to desktop Firefox or Chrome.
