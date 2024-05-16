SyntaxError: function statement requires a name
===============================================

 
The JavaScript exception \"function statement requires a name\" occurs
when there is a [function statement](../statements/function) in the code
that requires a name.


 
Message
-------

 
```text
SyntaxError: Function statements require a function name (V8-based)
SyntaxError: function statement requires a name (Firefox)
SyntaxError: Function statements must have a name. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
There is a [function statement](../statements/function) in the code that
requires a name. You\'ll need to check how functions are defined and if
you need to provide a name for it, or if the function in question needs
to be a function expression, an
[IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE), or if
the function code is placed correctly in this context at all.



 
Examples
--------


 
### Statements vs. expressions 

 
A *[function statement](../statements/function)* (or *function
declaration*) requires a name. This won\'t work:

 
 
[js]


```js
function () {
  return "Hello world";
}
// SyntaxError: function statement requires a name
```


You can use a [function expression](../operators/function) (assignment)
instead:

 
 
[js]


```js
const greet = function () {
  return "Hello world";
};
```


If your function is intended to be an
[IIFE](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression)
(Immediately Invoked Function Expression, which is a function that runs
as soon as it is defined) you will need to add a few more braces:

 
 
[js]


```js
(function () {
  // …
})();
```




 
### Labeled functions 

 
[Labels](../statements/label) are an entirely different feature from
function names. You can\'t use a label as a function name.

 
 
[js]


```js
function Greeter() {
  german: function () {
    return "Moin";
  }
}
// SyntaxError: function statement requires a name
```


In addition, labeled function declarations themselves are a deprecated
feature. Use regular function declarations instead.

 
 
[js]


```js
function Greeter() {
  function german() {
    return "Moin";
  }
}
```




 
### Object methods 

 
If you intended to create a method of an object, you will need to create
an object. The following syntax without a name after the `function`
keyword is valid then.

 
 
[js]


```js
const greeter = {
  german: function () {
    return "Moin";
  },
};
```


You can also use the [method syntax](../functions/method_definitions).

 
 
[js]


```js
const greeter = {
  german() {
    return "Moin";
  },
};
```




 
### Callback syntax 

 
Also, check your syntax when using callbacks. Braces and commas can
quickly get confusing.

 
 
[js]


```js
promise.then(
  function () {
    console.log("success");
  });
  function () {
    console.log("error");
}
// SyntaxError: function statement requires a name
```


Correct would be:

 
 
[js]


```js
promise.then(
  function () {
    console.log("success");
  },
  function () {
    console.log("error");
  },
);
```




 
See also 
--------

 
-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [`function`](../statements/function)
-   [`function` expression](../operators/function)
-   [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)
-   [Labeled statement](../statements/label)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unnamed_function_statement>

