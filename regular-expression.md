# Regular Expressions

Regular expressions are used in programming languages to match parts of strings. You create patterns to help you do that matching.

One way to test a regex is using the `.test()` method. The .test() method takes the regex, applies it to a string (which is placed inside the parentheses), and returns `true` or `false` if your pattern finds something or not.

```
let testStr = "freeCodeCamp";
let testRegex = /Code/;
testRegex.test(testStr);
```
