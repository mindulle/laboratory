Empty statement
===============

 
An **empty statement** is used to provide no statement, although the
JavaScript syntax would expect one.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
;
```




 
Description
-----------

 
The empty statement is a semicolon (`;`) indicating that no statement
will be executed, even if JavaScript syntax requires one.

The opposite behavior, where you want multiple statements, but
JavaScript only allows a single one, is possible using a [block
statement](block), which combines several statements into a single one.



 
Examples
--------


 
### Empty loop body 

 
The empty statement is sometimes used with loop statements. See the
following example with an empty loop body:

 
 
[js]


```js
const arr = [1, 2, 3];

// Assign all array values to 0
for (let i = 0; i < arr.length; arr[i++] = 0) /* empty statement */ ;

console.log(arr);
// [0, 0, 0]
```




 
### Unintentional usage 

 
It is a good idea to comment *intentional* use of the empty statement,
as it is not really obvious to distinguish from a normal semicolon.

In the following example, the usage is probably not intentional:

 
 
[js]


```js
if (condition);      // Caution, this "if" does nothing!
  killTheUniverse(); // So this always gets executed!!!
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-empty-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-empty-statement)

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

`Empty`

3

12

1

3

5

18

4

10.1

4.2

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Block statement](block)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/Empty>

