Inequality (!=)
===============

 
The `!=` operator checks whether its two operands are not equal,
returning a Boolean result. Unlike the [strict
inequality](strict_inequality) operator, it attempts to convert and
compare operands that are of different types.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x != y
```




 
Description
-----------

 
The inequality operator checks whether its operands are not equal. It is
the negation of the [equality](equality) operator so the following two
lines will always give the same result:

 
 
[js]


```js
x != y;

!(x == y);
```


For details of the comparison algorithm, see the page for the
[equality](equality) operator.

Like the equality operator, the inequality operator will attempt to
convert and compare operands of different types:

 
 
[js]


```js
3 != "3"; // false
```


To prevent this, and require that different types are considered to be
different, use the [strict inequality](strict_inequality) operator
instead:

 
 
[js]


```js
3 !== "3"; // true
```




 
Examples
--------


 
### Comparison with no type conversion 

 
 
 
[js]


```js
1 != 2; // true
"hello" != "hola"; // true

1 != 1; // false
"hello" != "hello"; // false
```




 
### Comparison with type conversion 

 
 
 
[js]


```js
"1" != 1; // false
1 != "1"; // false
0 != false; // false
0 != null; // true
0 != undefined; // true
0 != !!null; // false, look at Logical NOT operator
0 != !!undefined; // false, look at Logical NOT operator
null != undefined; // false

const number1 = new Number(3);
const number2 = new Number(3);
number1 != 3; // false
number1 != number2; // true
```




 
### Comparison of objects 

 
 
 
[js]


```js
const object1 = {
  key: "value",
};

const object2 = {
  key: "value",
};

console.log(object1 != object2); // true
console.log(object1 != object1); // false
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

`Inequality`

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

 
-   [Equality (`==`)](equality)
-   [Strict equality (`===`)](strict_equality)
-   [Strict inequality (`!==`)](strict_inequality)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality>

