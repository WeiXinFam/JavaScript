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
