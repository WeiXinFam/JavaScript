# ES6

### What is ES6?

ECMAScript, or ES, is a standardized version of JavaScript. Because all major browsers follow this specification, the terms ECMAScript and JavaScript are interchangeable.

### Variable keywords

#### Var vs Let---------------------

##### The biggest problem with Var

One of the biggest problems with declaring variables with the `var` keyword is that you can overwrite variable declarations without an error. This might not matter if the application is small. Instead when your code becomes larger, you might accidentally overwrite a variable that you did not intend to overwrite. Because this behavior does not throw an error, searching and fixing bugs becomes more difficult.

The `let` keyword is then introduced to solve this potential problem with `var` keyword. So unlike `var`, when using `let`, a variable with the same name can only be declared once. Note the `"use strict"`. This enables Strict Mode, which catches common coding mistakes and "unsafe" actions.

##### The scoping

When you declare a variable with the `var` keyword, it is declared globally, or locally if declared inside a function.

The `let` keyword behaves similarly, but with some extra features. When you declare a variable with the let keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression.

#### const declarations----------------

`const` has all the awesome features that `let` has, with the added bonus that variables declared using `const` are read-only. They are a constant value, which means that once a variable is assigned with `const`, it cannot be reassigned.

As you can see, trying to reassign a variable declared with `const` will throw an error. You should always name variables you don't want to reassign using the `const` keyword. This helps when you accidentally attempt to reassign a variable that is meant to stay constant. A common practice when naming constants is to use all uppercase letters, with words separated by an underscore.

However, it is important to understand that objects (including arrays and functions) assigned to a variable using `const` are still mutable. Using the `const` declaration only prevents reassignment of the variable identifier. You can use `Object.freeze` to prevent data mutation.

#### Notes

It is common for developers to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values (objects and arrays). In a later challenge you will see an example of a lowercase variable identifier being used for an array.

### Object functions

- `Object.freeze`: To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation. Once the object is frozen, you can no longer add, update, or delete properties from it. Any attempt at changing the object will be rejected without an error.

### Functions

In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. We don't need to name these functions because we do not reuse them anywhere else.

Usually  
`const myFunc = function() { const myVar = "value"; return myVar; }`

Arrow Function Syntax  
`const myFunc = () => { const myVar = "value"; return myVar; }`

When there is no function body, and only a return value, arrow function syntax allows you to omit the keyword return as well as the brackets surrounding the code. This helps simplify smaller functions into one-line statements:  
`const myFunc = () => "value";`

#### Function Parameters

If we have a single parameter, We can omit the enclosing the parentheses around the single parameter

`const doubler = item => item *2`

Also we can set default parameters like the following:

`const greeting = (name = "Anonymous") => "Hello " + name;`

ES6 also introduces the rest parameter for function parameters. With the rest parameter, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.

`function howMany(...args) { return "You have passed " + args.length + " arguments."; } console.log(howMany(0, 1, 2));`

The rest parameter eliminates the need to check the args array and allows us to apply `map()`, `filter()` and `reduce()` on the parameters array.

From above, we can see that there is a similar operator called spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected. For instance, `...arr` returns an unpacked array. In other words, it spreads the array. However, the spread operator only works in-place, like in an argument to a function or in an array literal.
