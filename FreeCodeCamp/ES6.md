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

When defining functions, we can remove the function keyword and colon together.

```
const person = {
  name: "Taylor",
  sayHello: function() {
    return `Hello! My name is ${this.name}.`;
  }
};
```

to

```
const person = {
  name: "Taylor",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  }
};
```

Note the function with no name, is also called anonymous function.

#### Function Parameters

If we have a single parameter, We can omit the enclosing the parentheses around the single parameter

`const doubler = item => item *2`

Also we can set default parameters like the following:

`const greeting = (name = "Anonymous") => "Hello " + name;`

ES6 also introduces the rest parameter for function parameters. With the rest parameter, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.

`function howMany(...args) { return "You have passed " + args.length + " arguments."; } console.log(howMany(0, 1, 2));`

The rest parameter eliminates the need to check the args array and allows us to apply `map()`, `filter()` and `reduce()` on the parameters array.

From above, we can see that there is a similar operator called spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected. For instance, `...arr` returns an unpacked array. In other words, it spreads the array. However, the spread operator only works in-place, like in an argument to a function or in an array literal.

#### Destructing assignment

Destructuring assignment is special syntax introduced in ES6, for neatly assigning values taken directly from an object

Given

```
const user = { name: 'John Doe', age: 34 };

const name = user.name;
const age = user.age;
```

We can use ES6 destructuring syntax

```
const { name, age } = user;
```

Destructuring allows you to assign a new variable name when extracting values. You can do this by putting the new name after a colon when assigning the value.

```
const { name: userName, age: userAge } = user;
```

We can also apply destructuring assignment to destruct values from nested objects.

```
const user = {
  johnDoe: {
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};

const { johnDoe: { age, email }} = user; // OR const { johnDoe: { age: userAge, email: userEmail }} = user;

```

Destructuring Arrays!  
One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.

```
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b); //a=1, b=2
```

We can also access the value at any index in an array with destructuring by using commas to reach the desired index

```
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c);
```

Destructing Assignment with the Rest parameter!

```
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b);
console.log(arr);
```

Result is similar to `Array.prototype.slice()`  
Variables a and b take the first and second values from the array. After that, because of the rest parameter's presence, arr gets the rest of the values in the form of an array. The rest element only works correctly as the last variable in the list. As in, you cannot use the rest parameter to catch a subarray that leaves out the last element of the original array.

Destructing Object in a function arguement!  
Instead of

```
const profileUpdate = (profileData) => {
  const { name, age, nationality, location } = profileData;

}
```

We can actually do this instead

```
const profileUpdate = ({ name, age, nationality, location }) => {

}
```

### Template Literals

Template literals allow you to create multi-line strings and to use string interpolation features to create strings.

Use backticks `` ` `` to wrap the string. And use `${variable}` syntax as a placeholder.

### Object Literals

Consider the following code:

```
const getMousePosition = (x, y) => ({
  x: x,
  y: y
});
```

`getMousePosition` is a simple function that returns an object containing two properties. ES6 provides the syntactic sugar to eliminate the redundancy of having to write `x: x`. You can simply write `x` once, and it will be converted to `x: x` (or something equivalent) under the hood. Here is the same function from above rewritten to use this new syntax:

```
const getMousePosition = (x, y) => ({ x, y });
```

### Create Objects

ES6 provides a new syntax to create objects, using the class keyword.

It should be noted that the class syntax is just syntax, and not a full-fledged class-based implementation of an object-oriented paradigm, unlike in languages such as Java, Python, Ruby, etc.

```
class SpaceShuttle {
  constructor(targetPlanet) {
    this.targetPlanet = targetPlanet;
  }
}
const zeus = new SpaceShuttle('Jupiter');

```

It should be noted that the `class` keyword declares a new function, to which a constructor is added. This constructor is invoked when `new` is called to create a new object.

Note: UpperCamelCase should be used by convention for ES6 class names, as in `SpaceShuttle` used above.

The `constructor` method is a special method for creating and initializing an object created with a class.

Note: It is convention to precede the name of a private variable with an underscore (\_). However, the practice itself does not make a variable private.

### Access Objects

We use _getters_ and _setters_ to obtain values form an object and set the value of a property within an object. This.

_getters_ - Getter functions are meant to simply return (get) the value of an object's private variable to the user without the user directly accessing the private variable.

_setters_ - Setter functions are meant to modify (set) the value of an object's private variable based on the value passed into the setter function. This change could involve calculations, or even overwriting the previous value completely.

### Modular Script

In order to make JavaScript more modular, clean, and maintainable; ES6 introduced a way to easily share code among JavaScript files. This involves exporting parts of a file for use in one or more other files, and importing the parts you need, where you need them. In order to take advantage of this functionality, you need to create a script in your HTML document with a type of `module`.

`<script type="module" src="filename.js"></script>`

### Share a Code

#### Export

In order to share it with these other files, you first need to `export` it.

```
export const add = (x, y) => {
  return x + y;
}
```

OR

```
const add = (x, y) => {
  return x + y;
}

export { add };
```

OR

```
export {add, subtract};
```

These are called named exports. Next we have export default.Usually you will use this syntax if only one value is being exported from a file. It is also used to create a fallback value for a file or module.

Since `export default` is used to declare a fallback value for a module or file, you can only have one value be a default export in each module or file. Additionally, you cannot use `export default` with `var`, `let`, or `const`

#### Import

```
import { add } from './math_functions.js';
```

The `./` tells the import to look for the `math_functions.js` file in the same folder as the current file. The relative file path (`./`) and file extension (`.js`) are required when using import in this way.

Or to import all

```
import * as myMathModule from "./math_functions.js";
```

`myMathModule` is just a variable name.

If we import a default export, we need to use a different `import` syntax:

```
import add from "./math_functions.js";
```

The syntax differs in one key place. The imported value, `add`, is not surrounded by curly braces (`{}`). add here is simply a variable name for whatever the default export of the `math_functions.js` file is. You can use any name here when importing a default.

### Javascript Promise

you use it to make a promise to do something, usually asynchronously. When the task completes, you either fulfill your promise or fail to do so. `Promise` is a constructor function, so you need to use the `new` keyword to create one. It takes a function, as its argument, with two parameters - `resolve` and `reject`. These are methods used to determine the outcome of the promise.

```
const myPromise = new Promise((resolve, reject) => {

});

```

A promise has three states: `pending`, `fulfilled`, and `rejected`. The promise you created in the last challenge is forever stuck in the `pending` state because you did not add a way to complete the promise. The `resolve` and `reject` parameters given to the promise argument are used to do this. `resolve` is used when you want your promise to succeed, and `reject` is used when you want it to fail.

```
const myPromise = new Promise((resolve, reject) => {
  if(condition here) {
    resolve("Promise was fulfilled");
  } else {
    reject("Promise was rejected");
  }
});
```

#### Handle Promises

Promises are most useful when you have a process that takes an unknown amount of time in your code (i.e. something asynchronous), often a server request. When you make a server request it takes some amount of time, and after it completes you usually want to do something with the response from the server. This can be achieved by using the `then` method. The `then` method is executed immediately after your promise is fulfilled with `resolve`.

```
myPromise.then(result => {

});
```

`result` comes from the argument given to the `resolve` method.
