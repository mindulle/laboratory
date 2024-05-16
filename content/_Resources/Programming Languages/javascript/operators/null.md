null
====

 
The `null` value represents the intentional absence of any object value.
It is one of JavaScript\'s [primitive
values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) and
is treated as
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) for
boolean operations.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
null
```




 
Description
-----------

 
The value `null` is written with a literal: `null`. `null` is not an
identifier for a property of the global object, like
[`undefined`](../global_objects/undefined) can be. Instead, `null`
expresses a lack of identification, indicating that a variable points to
no object. In APIs, `null` is often retrieved in a place where an object
can be expected but no object is relevant.

 
 
[js]


```js
// foo does not exist. It is not defined and has never been initialized:
foo; //ReferenceError: foo is not defined
```


 
 
[js]


```js
// foo is known to exist now but it has no type or value:
const foo = null;
foo; //null
```




 
Examples
--------


 
### Difference between `null` and `undefined` 

 
When checking for `null` or `undefined`, beware of the [differences
between equality (==) and identity (===)
operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators),
as the former performs type-conversion.

 
 
[js]


```js
typeof null; // "object" (not "null" for legacy reasons)
typeof undefined; // "undefined"
null === undefined; // false
null == undefined; // true
null === null; // true
null == null; // true
!null; // true
Number.isNaN(1 + null); // false
Number.isNaN(1 + undefined); // true
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-null-value]](https://tc39.es/ecma262/multipage/overview.html#sec-null-value)

  ------------------------------------------------------------------------------------------


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

`null`

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

 
-   [`undefined`](../global_objects/undefined)
-   [`NaN`](../global_objects/nan)
-   [`void`](void)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null>

