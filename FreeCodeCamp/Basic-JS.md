# Basic Javascript

- Comments: // and /\*\*/
- Data Types
  - undefined
  - null
  - boolean
  - string
  - symbol
  - bigint
  - number
  - object
  - type conversion:
    - parseInt
      - It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.
- variables:
  - store and manipulate data in a dynamic fashion. They do this by using a "label" to point to the data rather than using the data itself.
  - JavaScript variables when declared, it has an inital value of `undefined`
- keyword:
  - var
  - let
- note:
  - JS variables and function names are case sensitive. Best Practice is camelCase
  - Not all real numbers can accurately be represented in floating point. This can lead to rounding errors.
- operators:
  - `+`
  - `-`
  - `*`
  - `/`
  - `%`
    - The remainder operator is sometimes incorrectly referred to as the modulus operator. It is very similar to modulus, but does not work properly with negative numbers.
- increment/decrement:

  - `i++ == i=i+1`
  - `i-- == i=i-1`
  - `i+=5 == i=i+5`
  - `i-=5 == i= i-5`
  - `i*=5 == i=i*5`
  - `i/=5 == i= i/5`

- string operations:

  - use backslash(\)
    - to escape quote
      - or declare the new string with single quote at the beginning and at the end, with the other conversation string as double quotes
    - to escape character
  - can use single or double quotes
  - escape sequences in string
    - `\'` single quote
    - `\"` double qupte
    - `\\` backslash
    - `\n` newline
    - `\r` carriage return
    - `\t` tab
    - `\b` word boundary
    - `\f` form feed
  - `+` for concatenation
  - `+=` operator to concatenate a string onto the end of an existing string variable.
  - `<str variable>.length` to find the length of the string
  - Use Bracket Notation to Find the First Character in a String. They are zero-based indexing
  - String values are immutable, which means that they cannot be altered once created. Note that this does not mean that myStr cannot be changed, just that the individual characters of a string literal cannot be changed.

- data structure
  - array
    - nested/multi-dimensional
    - access the data inside arrays using indexes. Zero-based indexing
    - the entries of arrays are mutable and can be changed freely.
    - `.push()` takes one or more parameters and "pushes" them onto the end of the array.
    - `.pop()` is used to pop a value off of the end of an array.
    - `.shift()` works just like `.pop()`, except it removes the first element instead of the last.
    - `.unshift()` works exactly like `.push()`, but instead of adding the element at the end of the array, `unshift()` adds the element at the beginning of the array.
  - queue: New items can be added at the back of the queue and old items are taken off from the front of the queue.
- function

  - Basic structure:
    `function functionName(){}`
  - Parameters are variables that act as placeholders for the values that are to be input to a function when it is called.
  - The actual values that are input (or "passed") into a function when it is called are known as arguments.

  - Scopes  
    scope refers to the visibility of variables.
    - Global: declared outside function
    - Local: declared inside function
    - Variables which are declared without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var.
    - It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.
    - A function can include the return statement but it does not have to. In the case that the function doesn't have a return statement, when you call it, the function processes the inner code but the returned value is undefined.
  - Recursion is the concept that a function can be expressed in terms of itself.
    - Note: Recursive functions must have a base case when they return without calling the function again (in this example, when n <= 0), otherwise they can never finish executing.

- condition
  - basic structure
    - `if (condition is true) { statement is executed } else if (condition) else{}`
    - When a return statement is reached, the execution of the current function stops and control returns to the calling location.
  - switch
    `switch (num) { case value1: statement1; break; case value2: statement2; break; ... default: defaultStatement; break; }`
  - comparison operators
    - `==` equality
      - Type Coercion: to compare two different data types, we need to convert one type to the other
    - `===` Strict equality
      - does not perform a type conversion.
    - Note: In JavaScript, you can determine the type of a variable or a value with the `typeof` operator
    - `!=` inequality operator is the opposite of the equality operator. Like the equality operator, the inequality operator will convert data types of values while comparing.
    - The strict inequality operator (`!==`) is the logical opposite of the strict equality operator.The strict inequality operator will not convert data types.
    - Compares the values of two numbers
      - The greater than operator (`>`). The greater than operator will convert data types of values while comparing.
      - The greater than or equal to operator (`>=`). The greater than or equal to operator will convert data types while comparing.
      - The less than operator (`<`). The less than operator converts data types while comparing.
      - The less than or equal to operator (`<=`). The less than or equal to operator converts data types.
    - `&&` logical and operator.
    - `||` logical or operator
    - `a ? b : c` ternary operator
  - Objects
    - Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.
    - Objects are useful for storing data in a structured way, and can represent real world objects, like a cat.
    - if your object has any non-string properties, JavaScript will automatically typecast them as strings.
    - There are two ways to access the properties of an object: dot notation (.) and bracket notation ([]), similar to an array.
      - If the property of the object you are trying to access has a space in its name, you will need to use bracket notation.
      - Another use of bracket notation on objects is to access a property which is stored as the value of a variable. This can be very useful for iterating through an object's properties or when accessing a lookup table.
      - The sub-properties of objects can be accessed by chaining together the dot or bracket notation.
    - After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.
    - Add new property by dot or bracket notation
    - Delete properties eg `delete ourDog.bark;`
    - Objects can be thought of as a key/value storage, like a dictionary. If you have tabular data, you can use an object to lookup values rather than a switch statement or an if/else chain. This is most useful when you know that your input data is limited to a certain range.
    - use the `.hasOwnProperty(propname)` method of objects to determine if that object has the given property name.
  - loop
    - while
    - for (a; b; c), where a is the intialization statement, b is the condition statement, and c is the final expression.
    - do..while loop. Essentially, a do...while loop ensures that the code inside the loop will run at least once.
- Random
  - Math.random() generates a random decimal
  - `Math.floor(Math.random() * (max - min + 1)) + min`

Note:

- mad Lib
