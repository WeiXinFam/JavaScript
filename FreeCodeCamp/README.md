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
- function
  - Basic structure:
    `function functionName(){}`

Note:

- mad Lib
