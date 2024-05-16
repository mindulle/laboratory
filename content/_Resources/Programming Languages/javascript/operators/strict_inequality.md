Strict inequality (!==)
=======================

 
The `!==` operator checks whether its two operands are not equal,
returning a Boolean result. Unlike the [inequality](inequality)
operator, the strict inequality operator always considers operands of
different types to be different.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x !== y
```




 
Description
-----------

 
The strict inequality operator checks whether its operands are not
equal. It is the negation of the [strict equality](strict_equality)
operator so the following two lines will always give the same result:

 
 
[js]


```js
x !== y;

!(x === y);
```


For details of the comparison algorithm, see the page for the [strict
equality](strict_equality) operator.

Like the strict equality operator, the strict inequality operator will
always consider operands of different types to be different:

 
 
[js]


```js
3 !== "3"; // true
```




 
Examples
--------


 
### Comparing operands of the same type 

 
 
 
[js]


```js
"hello" !== "hello"; // false
"hello" !== "hola"; // true

3 !== 3; // false
3 !== 4; // true

true !== true; // false
true !== false; // true

null !== null; // false
```




 
### Comparing operands of different types 

 
 
 
[js]


```js
"3" !== 3; // true
true !== 1; // true
null !== undefined; // true
```




 
### Comparing objects 

 
 
 
[js]


```js
const object1 = {
  key: "value",
};

const object2 = {
  key: "value",
};

console.log(object1 !== object2); // true
console.log(object1 !== object1); // false
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-equality-operators]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-equality-operators)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`Strict_inequality`

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

 
-   [Equality (`==`)](equality)
-   [Inequality (`!=`)](inequality)
-   [Strict equality (`===`)](strict_equality)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality>

