# JavaScript Quick Start for Programmers

This is a one-day introduction to JavaScript for those who have completed
the foundation module in another language (Java, C#, Python).

## Materials

| Material                                                                                                              | Time |
|-----------------------------------------------------------------------------------------------------------------------|------|
| [Introduction to JavaScript for developers](https://www.youtube.com/playlist?list=PLqq-6Pq4lTTYFJxC9NLJ7dSTI5Z1WWB6K) (Until 35 - Anonymous Function Expressions) | ~2h15m |

### Reading (optional)

| Material                                                                                                      |
|---------------------------------------------------------------------------------------------------------------|
| [MDN JavaScript language overview](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Language_Overview) (Until Classes) |

## Preparation

- Download and install [Node.js](https://nodejs.org/en/download/) (the latest
  LTS Version)
  - MacOS with Homebrew: `brew install node`
  - Ubuntu: `sudo apt install nodejs`
- Download and install [Visual Studio Code](https://code.visualstudio.com/)
  - Recommended: install the [Live
    Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
    and [Code
    Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)
    VS Code extensions

## Material Review

- What is the difference between statically and dynamically typed languages?
  <!--
  - statically typed: data types are associated with variables
  - dynamically typed: data types are associated with values; a variable can
    store data of any type
  -->
- What is the difference between strongly and weakly (or loosely) typed
  languages?
  <!--
  - strongly typed: data types are enforced in operations (e.g. "a" + 1 results
    in an error)
  - weakly typed: data types are implicitly converted (e.g. "a" + 1 is converted
    into "a" + "1" evaluating to "a1")
  -->
- What is the difference between object-oriented and procedural programming?
  <!--
  - OOP: a program is composed of objects that encapsulate data and methods
    working with the data
  - procedural: a program is composed of data structures and functions that
    receive the data structures as arguments
  -->
- What is Node.js? How is it related to JavaScript?
  <!--
  - a runtime environment for executing JavaScript code outside the browser
  -->
- How can we run JavaScript in the browser?
  <!--
  - in the <script> element of a HTML file
  -->
- What is the entry point of a program?
  <!--
  - it doesn't have an entry point, all code in the global scope of the script
    gets executed
  -->
- What is "strict mode"?
  <!--
  - 'use strict' directive at the top of a script
  - it makes the interpreter throw exception for certain errors that non-strict
    mode would silently ignore
  -->
- What is the equivalent of `print` / `println` (`Write` / `WriteLine`)?
  <!--
  - console.log is the equivalent of println / WriteLine
  - process.stdout.write doesn't add new line, but it cannot be used in the
    browser
  -->
- How can we declare variables? And constants?
  <!--
  - with the var, let and const keywords
  - constants should get a value at declaration
  -->
- How are `var` and `let` different? Which one shall we use?
  <!--
  - they both declare a variable
  - var has function scope, let has block scope
  - let is preferred, var should be avoided
  -->
- What are JavaScript's primitive data types?
  <!--
  - boolean, number, string
  - there is no int, char
  -->
- How do we know the data type of the current value of a variable?
  <!--
  - we can use the typeof operator (it doesn't work for object (reference) types
    -- but in this mat. review we don't have to go into details)
  -->
- What is the difference between the `==` and `===` operators? Which one shall
  we use?
  <!--
  - ==: equality of values with implicit conversion; should be avoided
  - ===: equality of value and type; preferred
  -->
- What is `undefined`? How is it different from `null`?
  <!--
  - undefined: the variable hasn't been assigned any value
  - null: intentionally left empty (e.g. an optional value like middle name)
  -->
- How can we create an array? How many elements can it contain?
  <!--
  - with the square bracket operators: []
  - it can have any number of elements (similar to an ArrayList)
  -->
- What happens when we access an element of an array at an index that doesn't
  exist?
  <!--
  - it returns undefined, doesn't throw an exception
  -->
- What are the 3 types of `for` loop?
  <!--
  - for (let i = 0; i < array.length; i++) {}
  - for (let index in array) {}
  - for (let elem of array) {}
  -->
- What is the equivalent of a `HashMap` / `Dictionary`?
  <!--
  - an object: {}
  -->
- What are the 2 ways of accessing a property of an object?
  <!--
  - dot notation: obj.property
  - bracket notation: obj['property']
  -->
- What happens when we access a property of an object that doesn't exist?
  <!--
  - it returns undefined, doesn't throw an exception
  -->
- What are the 3 ways of defining a function?
  <!--
  - named function: function helloWorld() {}
  - function expression: const helloWorld = function() {};
  - arrow function: const helloWorld = () => {};
  -->
- How do we know the return type of a function?
  <!--
  - it depends on the value returned from the function, as it is a dynamically
    typed language
  - a function can return a value of any type
  - we can use the typeof operator
  -->

## Workshop

### Hello World with Node.js

Create an `index.js` file and add the following contents:

```js
'use strict';

function helloWorld() {
  console.log('Hello world!');
}

helloWorld();
```

Open the terminal in the same directory and execute the code with:

```sh
node index.js
```

It should print "Hello world!" to the standard output.

You can also select "Run Code" in VS Code, or, if you have the Code Runner
extension installed, press the Play button.

### Hello World in the browser

Create an `index.html` file in the same directory and copy-paste the
`helloWorld` function into the `<script>` element:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World</title>
  </head>
  <body>
    <script>
      'use strict';

      function helloWorld() {
        console.log('Hello world!');
      }

      helloWorld();
    </script>
  </body>
</html>
```

Open the file in a browser. If you have the Live Server VS Code extension
installed, click "Go Live!" in the status bar, and enter
[http://localhost:5500](http://localhost:5500) into the browser's address bar.
Open the browser's Developer Tools and select the Console tab. You should see
"Hello World!" printed on the console.

We can also load the script from an external file:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World</title>
  </head>
  <body>
    <script src="index.js"></script>
  </body>
</html>
```

Select the Network tab in the browser's Developer Tools and reload the page. You
can see that two files have been loaded, `index.html` and `index.js`.

## Exercises

These exercises should be familiar from the Foundation module, but this time
implement the solutions in JavaScript. Create a new `.js` file for each exercise
and execute it with `node`.

### Expressions and Control Flow

- [FizzBuzz](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/expressions-and-control-flow/fizz-buzz/fizz-buzz.js)
- [Draw triangle](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/expressions-and-control-flow/draw-triangle/draw-triangle.js)

### Functions

- [Summing](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/functions/sum/sum.js)
- [Factorial](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/functions/factorio/factorio.js)

### Arrays

- [Double items](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/arrays/double-items/double-items.js)
- [Sum all elements](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/arrays/sum-all/sum-all.js)

### Objects

- [Telephone book](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/data-structures/telephone-book/README.md)
- [Product database](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/data-structures/product-database/README.md)

### Extra Exercises

If you have time left, pick other exercises from each of the following topics:

- [Expressions and Control Flow](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/expressions-and-control-flow/js.md)
- [Functions](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/functions/js.md)
- [Arrays](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/arrays/js.md)
- [Data Structures](https://github.com/green-fox-academy/teaching-materials/blob/master/workshop/data-structures/js.md)
