throw
=====

 
The `throw` statement throws a user-defined exception. Execution of the
current function will stop (the statements after `throw` won\'t be
executed), and control will be passed to the first
[`catch`](try...catch) block in the call stack. If no `catch` block
exists among caller functions, the program will terminate.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
throw expression;
```


[`expression`](#expression)

:   The expression to throw.



 
Description
-----------

 
The `throw` statement is valid in all contexts where statements can be
used. Its execution generates an exception that penetrates through the
call stack. For more information on error bubbling and handling, see
[Control flow and error
handling](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling).

The `throw` keyword can be followed by any kind of expression, for
example:

 
 
[js]


```js
throw error; // Throws a previously defined value (e.g. within a catch block)
throw new Error("Required"); // Throws a new Error object
```


In practice, the exception you throw should *always* be an
[`Error`](../global_objects/error) object or an instance of an `Error`
subclass, such as [`RangeError`](../global_objects/rangeerror). This is
because code that catches the error may expect certain properties, such
as [`message`](../global_objects/error/message), to be present on the
caught value. For example, web APIs typically throw
[`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException)
instances, which inherit from `Error.prototype`.



 
### Automatic semicolon insertion 

 
The syntax forbids line terminators between the `throw` keyword and the
expression to be thrown.

 
 
[js]


```js
throw
new Error();
```


The code above is transformed by [automatic semicolon insertion
(ASI)](../lexical_grammar#automatic_semicolon_insertion) into:

 
 
[js]


```js
throw;
new Error();
```


This is invalid code, because unlike [`return`](return), `throw` must be
followed by an expression.

To avoid this problem (to prevent ASI), you could use parentheses:

 
 
[js]


```js
throw (
  new Error()
);
```




 
Examples
--------


 
### Throwing a user-defined error 

 
This example defines a function that throws a
[`TypeError`](../global_objects/typeerror) if the input is not of the
expected type.

 
 
[js]


```js
function isNumeric(x) {
  return ["number", "bigint"].includes(typeof x);
}

function sum(...values) {
  if (!values.every(isNumeric)) {
    throw new TypeError("Can only add numbers");
  }
  return values.reduce((a, b) => a + b);
}

console.log(sum(1, 2, 3)); // 6
try {
  sum("1", "2");
} catch (e) {
  console.error(e); // TypeError: Can only add numbers
}
```




 
### Throwing an existing object 

 
This example calls a callback-based async function, and throws an error
if the callback receives an error.

 
 
[js]


```js
readFile("foo.txt", (err, data) => {
  if (err) {
    throw err;
  }
  console.log(data);
});
```


Errors thrown this way are not catchable by the caller and will cause
the program to crash unless (a) the `readFile` function itself catches
the error, or (b) the program is running in a context that catches
top-level errors. You can handle errors more naturally by using the
[`Promise()`](../global_objects/promise/promise) constructor.

 
 
[js]


```js
function readFilePromise(path) {
  return new Promise((resolve, reject) => {
    readFile(path, (err, data) => {
      if (err) {
        reject(err);
      }
      resolve(data);
    });
  });
}

try {
  const data = await readFilePromise("foo.txt");
  console.log(data);
} catch (err) {
  console.error(err);
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-throw-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-throw-statement)

  -------------------------------------------------------------------------------------------------------------------------------------------


Browser compatibility 
---------------------

 


Desktop

Mobile

Server

Chrome

Edge

Firefox

Opera

Safari

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

WebView Android

Deno

Node.js

`throw`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`try...catch`](try...catch)
-   [`Error`](../global_objects/error)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw>

