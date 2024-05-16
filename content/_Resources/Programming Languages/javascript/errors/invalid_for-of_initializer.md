SyntaxError: a declaration in the head of a for-of loop can\'t have an initializer
==================================================================================

 
The JavaScript exception \"a declaration in the head of a for-of loop
can\'t have an initializer\" occurs when the head of a
[for\...of](../statements/for...of) loop contains an initializer
expression such as `for (const i = 0 of iterable)`. This is not allowed
in for-of loops.


 
Message
-------

 
```text
SyntaxError: for-of loop variable declaration may not have an initializer. (V8-based)
SyntaxError: a declaration in the head of a for-of loop can't have an initializer (Firefox)
SyntaxError: Cannot assign to the loop variable inside a for-of loop header. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
The head of a [for\...of](../statements/for...of) loop contains an
initializer expression. That is, a variable is declared and assigned a
value `for (const i = 0 of iterable)`. This is not allowed in for-of
loops. You might want a [`for`](../statements/for) loop that does allow
an initializer.



 
Examples
--------


 
### Invalid for-of loop 

 
 
 
[js]


```js
const iterable = [10, 20, 30];

for (const value = 50 of iterable) {
  console.log(value);
}

// SyntaxError: a declaration in the head of a for-of loop can't
// have an initializer
```




 
### Valid for-of loop 

 
You need to remove the initializer (`value = 50`) in the head of the
`for-of` loop. Maybe you intended to make 50 an offset value, in that
case you could add it to the loop body, for example.

 
 
[js]


```js
const iterable = [10, 20, 30];

for (let value of iterable) {
  value += 50;
  console.log(value);
}
// 60
// 70
// 80
```




 
See also 
--------

 
-   [`for...of`](../statements/for...of)
-   [`for...in`](../statements/for...in)
-   [`for`](../statements/for)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_for-of_initializer>

