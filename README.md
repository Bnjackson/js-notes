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

The object type is special. As they can contain multiple values, are mutable and are more complex than the primitive data types. Objects are used to store keyed collections of various data and more complex entities. 
 

### Primitive Data Types

Primitive data types are values that can only contain a single thing. All primitive types are immutable - meaning they cannot be changed after it is created. JavaScript allows us to work with primitive data types as if they were objects. This allows us to access methods that work via tempoary objects that are destroyed after the method runs.

The primitive data types are null, undefined, boolean, number, bigint, string and symbol.

All primitive types, except null, can be tested by the typeof operator. typeof null returns "object", so one has to use === null to test for null.

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

Math Operators
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

Comparison Operators 
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

Logical Operators - boolean logic
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