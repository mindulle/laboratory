Greater than (\>)
=================

 
The `>` operator returns `true` if the left operand is greater than the
right operand, and `false` otherwise.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x > y
```




 
Description
-----------

 
The operands are compared using the same algorithm as the [Less
than](less_than) operator, except the two operands are swapped. `x > y`
is generally equivalent to `y < x`, except that `x > y` coerces `x` to a
primitive before `y`, while `y < x` coerces `y` to a primitive before
`x`. Because coercion may have side effects, the order of the operands
may matter.



 
Examples
--------


 
### String to string comparison 

 
 
 
[js]


```js
"a" > "b"; // false
"a" > "a"; // false
"a" > "3"; // true
```




 
### String to number comparison 

 
 
 
[js]


```js
"5" > 3; // true
"3" > 3; // false
"3" > 5; // false

"hello" > 5; // false
5 > "hello"; // false

"5" > 3n; // true
"3" > 5n; // false
```




 
### Number to Number comparison 

 
 
 
[js]


```js
5 > 3; // true
3 > 3; // false
3 > 5; // false
```




 
### Number to BigInt comparison 

 
 
 
[js]


```js
5n > 3; // true
3 > 5n; // false
```




 
### Comparing Boolean, null, undefined, NaN 

 
 
 
[js]


```js
true > false; // true
false > true; // false

true > 0; // true
true > 1; // false

null > 0; // false
1 > null; // true

undefined > 3; // false
3 > undefined; // false

3 > NaN; // false
NaN > 3; // false
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-relational-operators]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-relational-operators)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`Greater_than`

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

 
-   [Greater than or equal (`>=`)](greater_than_or_equal)
-   [Less than (`<`)](less_than)
-   [Less than or equal (`<=`)](less_than_or_equal)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than>

