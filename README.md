# JavaScript Notes 

## Comments

```
//single line comments
/*
multi 
line 
comments
*/
```

## Variables, Data Types and Operators 

### Variables

Variables - Named storage for data. JS is a dynamically typed language meaning that variables are not directly associated with any particular value type, and variables can be assigned and re-assigned values of all types.

```
var oldVariable; //Var is rarely used since let and const were introduced in ES6. Var is function scoped and var variables are "hoisted" to the top of their scope. Meaning they can be accessed before they declared.

let changeVariable; //Creates variables that can be reassigned.

const constantVariable; //Creates variables that are constant and cannot be reassigned.
```

Type coercion - JavaScript is a weakly typed language meaning it allows type conversion when an operation involves mismatched types, instead of throwing type errors.

```
let string = '5';
let number = 5;
let sum = string + number; //The value of sum will be the string '55' the number is coerced into a string and then the two values are concatenated together.
```

Mutable - Mutable values are ones that can be changed. Objects and arrays are mutable by default, primitive values cannot be mutated but the variable can be reassigned. 

### Data Types

A value in JS is always of a certain type. In JS there are eight data types, seven primitive data types and objects.

#### Objects 

The object type is special. As they can contain multiple values, are mutable and are more complex than the primitive data types. Objects are used to store keyed collections of various types of data and more complex entities. 

In JavaScript both arrays and functions are objects, meaning they can be assigned to variables, passed as arguments to functions, and used like any other object.

Objects are unordered sequences of key-value pairs the keys are called "properties" they are arbitary strings and the values are any data type, each property can be used to look up(reference) the value associated with it.

Objects can be used to organize code better instead of using multiple variables we can store things in a single object. Objects are usually created to represent entities of the real world like users, items, orders and so on.

```
const john = { // an object
  firstName:'John', //by key 'firstName' value 'john'
  lastName:'Davies', //by key 'lastName' value 'Davies'
  age:24,//by key 'age' store value 24
  family: ['Jane', 'Mark', 'Emily'],//Objects can store arrays
  'is Married': false, //We can create multiword propety names they must be quoted.
};

console.log(john.firstName); //We can access objects using dot notation
const x = 'age';
console.log(john[x]); //Will print 24 useful logic for accessing data from an array.
john.job = 'programmer';//We can add to the object using name.key = value
john.age = 29;//We can also assign new values to the properties;
john["Favourite Film"] = Big Lebowski; //We use [] to create multiword propety names.
delete john.job; //We can delete a property from an object with the delete operator.
```

### Primitive Data Types

Primitive data types are values that can only contain a single thing. All primitive types are immutable - meaning they cannot be changed after it is created. JavaScript allows us to work with primitive data types as if they were objects. This allows us to access methods that work via tempoary objects that are destroyed after the method runs.

The primitive data types are null, undefined, boolean, number, bigint, string and symbol.

All primitive types, except null, can be tested by the typeof operator. typeof null returns "object", so one has to use === null to test for null.

```
typeof "John"                 // Returns "string"
typeof 3.14                   // Returns "number"
typeof NaN                    // Returns "number"
typeof false                  // Returns "boolean"
typeof [1,2,3,4]              // Returns "object"
typeof {name:'John', age:34}  // Returns "object"
typeof new Date()             // Returns "object"
typeof function () {}         // Returns "function"
typeof myCar                  // Returns "undefined" *
typeof null                   // Returns "object"
```

#### Number 

Numbers represent both integers and floating point numbers. There are also special numeric values including infinity, -Infinity and NaN.

The math object is a built in object that has a library of properties and methods for mathemetically use. The math object works with the number type. 
Some useful math methods include. 

```
Math.floor(); //Returns a rounded down integer.
Math.ceil(); //Returns a rounded up integer.
Math.round(); //Returns a integeer rounded to the nearest integer.
Math.random(); //Returns a random number between 0 and 1.
```

We can use Number() to convert a value into a number. 

If we need to get a number from a string we can use the parseInt and the parseFloat method.

```
parseInt(150px); //Returns a integer - 100
parseFloat($2450); //Returns a float - 2450
```

#### String 

A string is a sequence of characters, used for text wrapped in ''(single), ""(double) or backtick(``) quotation marks.

Using backticks allow us to create a "extended functionality" quotes that allow us to embed variables and expressions into a string by wrapping them in a ${}.

We can access the characters of a string using bracket notation []. We cannot change characters like we would an array using bracket notation. As strings are immutable.

```
let str = 'hi';
str[0] = 'x'; //Error 

//The workaround is to reasign or create a new string and assign the value to it
str = x + str[1]; //'xi'
```

Some useful methods for strings include...

```
str.length(); //Returns the length of the string
str.toLowerCase(); //Returns a lowercase string
str.toUpperCase(); //Returns a capatilized string
str.replace(); //Replaces a specified value with another value in the string
```

Comparing Strings - Strings are compared character by character in alphabetical order. If the first character of one string is greater or less than the other strings. Then the first string is greater or less than the second.
If both characters are the same repeat with the rest of the characters, if all are equal then the two strings are equal.

```
console.log("z" > "a")//True

console.log("a" > "Z")//true - One oddity is that a lowercase letter is always greater than the uppercase.
```

#### Boolean 

Booleans are a logical data type that can be true or false. Boolean values can come as a result of comparisons. In JS everything with a value is true and everything without a value is false.

#### Null 

The null type can only have one value: null. The null value represents the intentional absence of an object. 

#### Undefined

The undefined type is inhabitated by exactly one value: undefined. Undefiend indicates the absence of a value.

#### BigInt 

The BigInt type can represent integers larger than the limit for Numbers and allows for them to be operated on.

#### Symbol

A Symbol is a unique and immutable primitive value and may be used as the key of an Object property. In some programming languages, Symbols are called "atoms". The purpose of symbols is to create unique property keys that are guaranteed not to clash with keys from other code.

### Operators 

Operators are used to assign values, compare values, perform arithmetic operations and more.

#### Math Operators
```
+ //Addition
- //Subtraction 
* //Multiplication
** //Exponentiation
/ //Diviion
% //Modulus (remainder)
++ //Increment 
-- //Decrement
```

Increment and decrement operators can be applied both before and after the operator. Both postfix and prefix increase or decrease the value by 1. The ++ or -- can be applied both before and after the variable.

Postfix - counter++ - The postfix form returns the original value of the variable of the variable before the increment/decrement

```
let counter = 2;
console.log(counter++); //2 Returns the original value prior to the increment.
```

Prefix - ++counter - The prefix form returns the value after the increment/decrement.

```
let counter = 2;
console.log(++counter); //3 Returns the incremented value.
```

#### Comparison Operators 
```
1 < 2 //Less than
2 > 1 //Greater than
1 <= 2 //Less than or equal too
2 >= 1 //Greater than or equal too
5 == '5'//Equal value, type coercion, data types do not have to match
1 === 1 //Equal value, same type
1 != 2 //Not equal too, with type coercion
1 !== 2 //Not equal strict without type coercion
```

#### Logical Operators - boolean logic
```
&& - The and operator checks if the conditions on its left and right are true before running
|| - The or operator Only requires one condition to be true
!  - The not operator inverts true or false values.
```

Short-circuit evaluation is when the second argument is executed or evaluated only if the first argument does not suffice to determine the value of the expression. When the fist argument of && is false the overall value must be false and when the first argument of || is true then the overall value must be true.

```
let trueOrFalse = true || false; //The value will be true because an || operator only requires one true argument.
```
Assignment operators - are used to assign values to variables
```
= - Assigns a value to a variable
+= - Adds a value to a variable
-= - Subtracts value from a variable
*= - Multiplies a variable
/= - Divides a variable
%= - Assigns a remainder variable
```

Operator Precedence - Determines how operators are parsed concerning each other. Operators with higher precedence become the operands of operators with lower precedence.

String Operators
```
+ - Used to concatenate (add) strings.
+= - Also used to add strings together.
```

Truthy and Falsy - Each value has an inherent boolean value known as a truthy or falsy. They can be used to check if a variable exists for example to check if a user has a username.

```
let defaultName;
if (username) {
  defaultName = username;
} else {
  defaultName = 'Stranger';
}
```

Falsy Values: undefined, null, false, 0, '' (empty string), NaN. - Values considered false when evaluated in an if else statement.

Truthy Values: '0', 'false', [](an empty array), {}(an empty object), function(){}(an empty function) - Values considered true when evaluated in an if else statement.

We can check if a value is truthy or falsey using a conditional.

```
if(value) //will run if value is truthy.
if(!value) //Will run if value is falsey.
value ? /*will run if truthy*/ : /*will run if falsey*/
``` 

## Logic and Conditionals
Code is run in order from the first line in a file to the last line. Structures like conditonals, loops and functions allow us to change the control flow. 

Conditional statements tell the computer to execute certain actions, provided certain conditions are met. They allow a program to make decisions based on different inputs. 
Specifically they execute a specific action based on the results of an outcome of true or false.


### if...else statements

Conditional statements will perform different actions based on different conditions. They are useful for when you need to perform different actions based on different conditions. 

```
const colour = 'red';
if (colour === 'red') {
    console.log('The colour is red.');
} else if (colour === 'blue') {
    console.log('The colour is blue');
} else {
    console.log('The colour is neither red or blue');
}
```

The if statement evaluates the condtion in its parentheses and converts the result to a boolean. If true it executes a block of code. 


The else if statement is used when we need to test different conditions if the first condition is false.

The else statement is to specify a block of code to be executed if the previous conditions are false.

### Switch statements

Switch Statements provide an alternative syntax to if else statements. A switch statement is useful when having to write many else if statements. If a break is ommited from a case the following case statements are executed until a break is encountered.

```
const groceryItem = 'tomato';
switch (groceryItem) {
  case 'onion':
    console.log('Onions are £0.30');
    break;
  case 'lime':
    console.log('Limes are £0.60');
    break;
  case 'pepper':
    console.log('Peppers are £0.45');
    break;
  case 'tomato':
    console.log('Tomatos are £0.50');
    break;
  default:
    console.log('Invalid Item');
}
```
If the case matches with the expression, then the code within the case will run. If no case matches then the default will run instead.

### Ternary Operators

Are the only JavaScript operator that takes three operands, a condition followed by a question mark (?) then an expression to execute if the condition is truthy follwed by a colon (:) and finally the expression to execute if the conditon is falsy. This operator is used as a alternative for the if...else statement.

```
const score = 75;

const passingScore = score > 70 ? true : false;
```

Ternary operators allow you to write shorter and cleaner condtions. They are a good alternative for shorter if...else statements, but can make code hard to read if used as an alternative to longer conditionals.

## Arrays 

Primitive data types can only store 1 value at a time. If we need to store 100 values, we would need 100 seperate variables. To handle such situations programming languages provide a solution, arrays. An array is a data structure that can store a collection of data under a single variable name.

Arrays are a type of object, howver unlike objects they are numbered. Arrays are zero-indexed meaning that the first item in a an array starts at index 0 and the last item is at the value of the array's length property minus 1. 

Arrays in JavaScript can store a collection of various data types and objects unlike in some other languages. 

Arrays are useful for storing a list of something: users, goods, HTML elements etc. Arrays provide ways to manage the order of elements unlike objects.

We create an array using [] and we assign it to a named variable. Each item in an array has a numbered position.

```
let numbersArr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
console.log(numbersArr[0]) //We can access individual items in an array using bracket notation with the items index. 
numbersArr[10] = 11; //We can add or change the items in an array.
numbersArr.length; //The return property returns the length of an array.
```

### Nested Arrays

We can store arrays in other arrays. When an array contains another array it is known as a nested array. To access nested arrays we use bracket notation with the index value.

```
nestedArr[1]; // Output: [2, 3]. nestedArr[1] will get the value of the element in index 1 which is array [2, 3].

nestedArr[1][0]; // Returns: 2. We can chain on more index values.
```

### Array Methods
 
Methods that modify the original array are known as mutator methods, and methods that return a new value or representation are reffered to as accessor methods. Methods that operate on every item in an array, one at a time are known as itteration methods.

There are some useful methods for arrays including. 

```
arr.push('newElement'); //.push() adds an element to the end of an array.
arr.unshift('newElement); //.unshift() adds an element to the beggining of an array.
arr.pop() //.pop() removes the last element from an array. The removed element can be assigned to a variable.
arr.shift() //.shift() removes the first element from an array. The removed element can be assigned to a varaible/
arr.splice(0, 2, 'item1', 'item2') //.splice() is used to add and remove items from an array. Thr first parameter(0) defines the position where new elements should be added, the second parameter defines how many elements should be removed(2). The rest of the paramaters ('item1', 'item2') define the new elements to be added.
arr.join(' ') //join.() converts an array into a string of array values. It also allows us to specify the seperator between the array values.  
let myFamily = myParents.concat(mySiblings); //.concat() creates a new arrray by merging(concatenating) existing arrays. The concat method can take any number of arrays or strings as arguments. The method does also not change the existing arrays, but return a new array.

```

### Iterator Array Methods 

There are several built in array methods that allow us to iterate over arrays.
These built-in methods help us iterate through arrays and are called “iteration methods” or “iterators”. Iterators are methods that are called on arrays to manipulate elements and return some values.

Using methods that iterate over an array can often result in more concise, expressive, and readable code than using traditional loops in JavaScript. They can also simplify common operations such as transforming, filtering, and aggregating arrays.

#### .forEach()

This method executes a block of code or a function for each element in an array. 

```
let namesArray = ['Sarah', 'John', 'Arthur', 'Susie'];

namesArray.forEach((element) => {
    console.log(element);
});
```

When you need to perform an operation on each element of an array: Using the forEach() method can be a more concise way to perform an operation on each element of an array than using a traditional for loop. For example, the above code logs each element of an array to the console:

#### .map()

This method returns a new array with the updated elements after calling a callback function on every element in the array.

```
let uppercaseNames = namesArray.map((element) => {
    return element.toUppercase();
});
```

The original array doesn’t change. This is used to alter each item individually to create a new transformed array.

#### .filter() 

The .filter() method checks each element in an array to see if it meets a condition. It returns a new array whith the elements that meet the condition. 

```
let shortNamesArray = namesArray.filter((element) => element.length < 5);
```

The callback function for the .filter() method should return true or false depending on if the element length is shorter than 5.
The elements that cause the callback function to return true are added to the new array.

#### .find() 

This method returns the value of the first element of an array which satisfies a condition. The method will return undefined if none of the elements satisfies this condition.

```
let findJohn = namesArray.find((element) => element === 'John');
```

#### .findIndex() 

Similar to find method. Their difference is that this method returns the index of the first element of an array which satisfies the condition set. The method will return -1 if none of the elements satisfies the condition.

```
let findJohnIndex = namesArray.findIndex((element) => element === 'John');
```

#### .reduce()

The reduce method is used to reduce the array to a single value. It executes a provided function for each value of the array (from left-to-right). The return value of the function is stored in an accumulator.

```
let allNames = namesArray.reduce(
    (all, name) => all += ' ' + name
);
```

In this example, Reduce accepts two parameters, the accumulator (all) and the current element (name). The reduce method iterates through each element in the array as a for-loop. In the accumulator, we store the concatenated string.

#### .some()

The .some() method tests if some of the elements in the array pass a condition. It will return true if any values meet the condtion and false if none do. The return value is a boolean.

```
let isString = namesArray.some(
    (name) => typeof name === 'number';
);
// Expected output: false
```

#### .every()

The .every() method tests whether all elements in the array pass the test implemented by the provided function. It returns a boolean value.

```
let allStrings = namesArray.every(
    (name) => typeof name === 'string'
); 
// Expected output: true
```

#### .sort()

The .sort() method sorts the elements in an array alphabetically and in ascending order and returns the the newly sorted array. 

```
const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);
// Expected output: Array ["Dec", "Feb", "Jan", "March"]
```

This method works well for strings. However when we try to sort numbers like strings, 25 is sorted higher than 100, because 2 is greater than 1. Because of this sort() method will produce incorrect results when sorting numbers. We can use a compare function to fix this.

```
let numbersArr = [100, 45, 62, 76, 909, 23, 97, 53, 32, 16, 36, 111];
let sortedArr = numbersArr.sort(
    (a, b) => a - b
);
```

The compare function takes in two numbers at a time e.g. 100 - 45. As this result is a positive number, 100 will be sorted ahead of 45. If the result was negative then outcome would be reversed. This process continues until all numbers are sorted.  

## Loops

A loop is a programming tool that repeats a set of instructions until a specified condition called a stopping condition is reached. Loops iterate or repeat an action until a specific condition is met. When the condition is met, the loop stops and the computer moves on.

When programming we often need to repeat actions. Instead of having to write the same code again and again, wasting time and making the code harder to read through. We can use loops to repeat instructions multiple times until a condition is met.

If we are not careful we can create infinite loops that will slow down or crash the program. 
To insure this does not happen we should use stopping conditions that stop the loop once we have reached the specified condition. We can also use the break keyword to stop a loop even if the stopping condition is not met. 

### for loops 

A typical for loop includes an iterator variable that usually appears in all three expressions. The iterator variable is intialized checked against the stopping condition, and assigned a new value on each loop iteration. Iterator variables can have any name, but its best practise to use a descriptive names.

A for loop contains three expressions seperated by ; inside the ()
- An intialization starts the loop and can also be used to declare the iterator variable.
- A stopping condition is the condition that the iterator variable is evaluated against - if the condition evaluates to true the code block will run, and if it evaluates to false the code will stop.
- An iteration statement is used to update the iterator variable on each loop.

```
for (let = counter = 0; //intialization start of the loop and declared as variable.
   counter < 4; //Stopping condition iterator is evaluated against this.
   counter++) { //iteration statement used to update the iterator.
   console.log(counter);
}
//It is a naming convention to name our counting variables i
```

### for...in loops

Looping through arrays is one of the most common uses of for loops. However we cannot loop through an object as we would an array, becuase the key value pairs in objects are not ordered. we have to use the for...in loop.

```
const object = { a: 1, b: 2, c: 3 };

for (const property in object) {
    console.log(`${property}: ${object[property]}`);
}
```

The for...in loop iterates through the properties of an object. The variable is used to access the value of the property.

### While loop

While the condition is true the loop will execute. while loops are used when we dont know how many times the loop should run. While loops can create infinite loops that should be avoided as they can use too much processing power.

```
let i = 0;
    while (i < 4) {
    console.log(i);
    i++;
}
```

### do...while loops 

In some cases you want a piece of code to run at least once and then loop based on specific condition after its intial run. A do...while statement will run until a specified condition is no longer met.

```
let i = 0;
do {
    alert(i);//The body of the loop will execute at least once regardless if true.
    i++;
} while (i < 3);
```

### Nested loops 

When we have a loop running inside another loop that is called a nested loop. One use for nested loops is to compare the elements in two arrays. For each round of the outer loop, the inner loop will run completely.

```
for (i = 0; i < outerLimit; i++) {
  for (j = 0; j < innerLimit; j++) {
    // code to be executed
  }
}
```
In the above code, for each iteration of the outer loop the inner loop will run as many times as the value of innerLimit. 

## Functions 

Functions are one of the fundamental building blocks of JavaScript. A function in JavaScript is similar to a procedure a set of statements that performs a task or calculates a value, but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output. 

A function is a reusable block of code. It is executed when something evokes it (calls it). They can be used with different arguments, to produce different results. 

Functions can access internal variables and outer variables, however code outside the function cannot access any variables declared inside a function. 

A function should be short and do exactly what there name suggests. Two independent actions usually deserve two functions. Using several small functions over one large function is easier to test, debug and read. 

No matter what syntax is used to create a function, a function in JavaScript is a value. They can be passed to other functions, they can be made into methods, they can be stored in arrays or stored in variables.

### Function parameters 

We can pass data into a function using parameters. A parameter is a named variable passed into a function. Parameter variables are used to import arguments into functions (when a value is imported into a function it is called an argument). If a parameter value is not provided then its value becomes undefined. 

We can create default parameters for when a value is not passed into the function.  

```
function showMessage(message = 'no message given') {
    console.log(message)
}

message();
// expected output: no message given
```

#### Rest parameter

The rest parameter allows us to represent an indefinite number of arguments as an array. A function can be prefixed with ... which will cause all remaining arguments to be placed within a array.

```
function sum(...theArgs) {
  return theArgs.reduce((previous, current) => {
    return previous + current;
  });
}

console.log(sum(1, 2, 3));
// expected output: 6

console.log(sum(1, 2, 3, 4));
// expected output: 10

```

#### Spread operator 

ES6 introduced the spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected.

```
function sum(x, y, z) {
  return x + y + z;
}
const arrayNumbers = [1, 2, 3];

console.log(sum(...arrayNumbers));
//expected output: 6
```

### Return

A function can return a value by using the return keyword in a function and then calling the function. 

```
function sum(a, b) {
  return a + b;
}

let result = sum(1, 2);
alert( result ); // 3
```

A function immediately stops at the point where return is called. 

### naming a function 

Functions are actions so their name is usually prefixed by a verb. It should be brief but descriptive, accurate and describe what the function does, so that someone who reads the code gets an indication of what the function does.

For instance....
show - shows something
get - return a value
calc - calculate something
create - create something
check - check something and retun a boolean
push
apply
compute
post

### Function declaration

The most commonly used way to create a function is using function declarations. The function keyword goes first then, the function name, then the parameters, and between {} goes the function body.
The function is called by its name followed by ().

```
function printMessage() {
    console.log('Hello World!');
}

printMessage();
```

Function declarations are hoisted meaning no matter where they are declared they are hoisted to the top of their scope.
Function declarations can also be used as constructors and have a prototype property.


### Function expressions 

There are many different syntaxes for creating a function, so far we have only used function declarations. Another syntax for creating a function is called a function expression. A function expression is a function assigned to a variable. 

```
let printMessage() {
    console.log("Hello World!);
}
```

 Function expressions are not hoisted, which means that they must be defined before they are called. This makes function expressions useful for functions that are only used in specific parts of your code.


### Arrow functions 

There’s another very simple and concise syntax for creating functions, that’s often better than Function Expressions. its called arrow functions.

```
let printMessage = () => console.log('Hello World!');
```

Arrow functions have a very convenient syntax and are very useful for smaller functions, such as callbacks and one line functions. When there is no function body, and only a return value we can omit the return keyword as well as the brackets surrounding the code.

We can also use arrow functions for longer more complex functions. But also have to use curly braces and the return keyword.

```
let add = (a, b) => {
    let result = a + b;
    return result;
}

sum(1, 2);
```

### Anonymous functions 

An Anonymous function is a function without a name it wont do anything on its own. You generally use an Anonymous function with an event handler, so the function runs in response to an event such as a button being clicked.

```
const myButton = document.querySelector('button');

myButton.onclick = function() {
  console.log('Button has been clicked');
}
```

### Higher-Order functions 

Functions that operate on other functions, either by taking them as arguments or by returning them, are called higher-order functions. We call the function that gets passed in as parameters and invoked callback functions because they get called during the execution of the higher-order function.

Its called a higher-order function because instead of strings, numbers or booleans it goes higher to operate on functions. 