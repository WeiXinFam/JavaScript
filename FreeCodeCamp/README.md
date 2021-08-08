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

Note:

- mad Lib
