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

Variables - Named storage for data. JS is a dynamically typed language meaning that there exist data types but variables are not bound to any of them. 

```
var oldVariable; //Var is rarely used since let and const were introduced in ES6. Var is function scoped and var variables are "hoisted" to the top of their scope. Meaning they can be accessed before they declared.

let changeVariable; //Creates variables that can be reassigned.

const constantVariable; //Creates variables that are constant and cannot be reassigned.
```

Type coercion - JavaScript automatically converts types from one to another when needed. 

```
let string = '5';
let number = 5;
let sum = string + number; //The value of sum will be the string '55' the number is coerced into a string and then the two values are concatenated together.
```

Mutable - Mutable values are ones that can be changed. Objects and arrays are mutable by default, primitive values cannot be mutated but the variable can be reassigned. 

