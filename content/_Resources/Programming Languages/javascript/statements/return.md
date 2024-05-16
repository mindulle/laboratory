return
======

 
The `return` statement ends function execution and specifies a value to
be returned to the function caller.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
return;
return expression;
```


[`expression`](#expression) [Optional]

:   The expression whose value is to be returned. If omitted,
    `undefined` is returned.



 
Description
-----------

 
The `return` statement can only be used within function bodies. When a
`return` statement is used in a function body, the execution of the
function is stopped. The `return` statement has different effects when
placed in different functions:

-   In a plain function, the call to that function evaluates to the
    return value.
-   In an async function, the produced promise is resolved with the
    returned value.
-   In a generator function, the produced generator object\'s `next()`
    method returns `{ done: true, value: returnedValue }`.
-   In an async generator function, the produced async generator
    object\'s `next()` method returns a promise fulfilled with
    `{ done: true, value: returnedValue }`.

If a `return` statement is executed within a [`try`](try...catch) block,
its `finally` block, if present, is first executed, before the value is
actually returned.



 
### Automatic semicolon insertion 

 
The syntax forbids line terminators between the `return` keyword and the
expression to be returned.

 
 
[js]


```js
return
a + b;
```


The code above is transformed by [automatic semicolon insertion
(ASI)](../lexical_grammar#automatic_semicolon_insertion) into:

 
 
[js]


```js
return;
a + b;
```


This makes the function return `undefined` and the `a + b` expression is
never evaluated. This may generate [a warning in the
console](../errors/stmt_after_return).

To avoid this problem (to prevent ASI), you could use parentheses:

 
 
[js]


```js
return (
  a + b
);
```




 
Examples
--------


 
### Interrupt a function 

 
A function immediately stops at the point where `return` is called.

 
 
[js]


```js
function counter() {
  // Infinite loop
  for (let count = 1; ; count++) {
    console.log(`${count}A`); // Until 5
    if (count === 5) {
      return;
    }
    console.log(`${count}B`); // Until 4
  }
  console.log(`${count}C`); // Never appears
}

counter();

// Logs:
// 1A
// 1B
// 2A
// 2B
// 3A
// 3B
// 4A
// 4B
// 5A
```




 
### Returning a function 

 
See also the article about
[Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures).

 
 
[js]


```js
function magic() {
  return function calc(x) {
    return x * 42;
  };
}

const answer = magic();
answer(1337); // 56154
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-return-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-return-statement)

  ---------------------------------------------------------------------------------------------------------------------------------------------


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

`return`

1

12

1

3

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

 
-   [Functions](../functions)
-   [Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return>

