SyntaxError: for-in loop head declarations may not have initializers
====================================================================

 
The JavaScript [strict mode](../strict_mode)-only exception \"for-in
loop head declarations may not have initializers\" occurs when the head
of a [for\...in](../statements/for...in) contains an initializer
expression, such as `for (var i = 0 in obj)`. This is not allowed in
for-in loops in strict mode. In addition, lexical declarations with
initializers like `for (const i = 0 in obj)` are not allowed outside
strict mode either.


 
Message
-------

 
```text
SyntaxError: for-in loop variable declaration may not have an initializer. (V8-based)
SyntaxError: for-in loop head declarations may not have initializers (Firefox)
SyntaxError: a lexical declaration in the head of a for-in loop can't have an initializer (Firefox)
SyntaxError: Cannot assign to the loop variable inside a for-in loop header. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror).



 
What went wrong? 
----------------

 
The head of a [for\...in](../statements/for...in) loop contains an
initializer expression. That is, a variable is declared and assigned a
value `for (var i = 0 in obj)`. In non-strict mode, this head
declaration is silently ignored and behaves like `for (var i in obj)`.
In [strict mode](../strict_mode), however, a `SyntaxError` is thrown. In
addition, lexical declarations with initializers like
`for (const i = 0 in obj)` are not allowed outside strict mode either,
and will always produce a `SyntaxError`.



 
Examples
--------

 
This example throws a `SyntaxError`:

 
 
[js]


```js
const obj = { a: 1, b: 2, c: 3 };

for (const i = 0 in obj) {
  console.log(obj[i]);
}

// SyntaxError: for-in loop head declarations may not have initializers
```




 
### Valid for-in loop 

 
You can remove the initializer (`i = 0`) in the head of the for-in loop.

 
 
[js]


```js
const obj = { a: 1, b: 2, c: 3 };

for (const i in obj) {
  console.log(obj[i]);
}
```




 
### Array iteration 

 
The for\...in loop [shouldn\'t be used for Array
iteration](../statements/for...in#array_iteration_and_for...in). Did you
intend to use a [`for`](../statements/for) loop instead of a `for-in`
loop to iterate an [`Array`](../global_objects/array)? The `for` loop
allows you to set an initializer then as well:

 
 
[js]


```js
const arr = ["a", "b", "c"];

for (let i = 2; i < arr.length; i++) {
  console.log(arr[i]);
}

// "c"
```




 
See also 
--------

 
-   [`for...in`](../statements/for...in)
-   [`for...of`](../statements/for...of)
-   [`for`](../statements/for)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_for-in_initializer>

