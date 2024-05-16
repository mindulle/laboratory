Logical AND assignment (&&=)
============================

 
The `&&=` operator only evaluates the right operand and assigns to the
left if the left operand is
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x &&= y
```




 
Description
-----------

 
Logical AND assignment
[*short-circuits*](operator_precedence#short-circuiting), meaning that
`x &&= y` is equivalent to `x && (x = y)`, except that the expression
`x` is only evaluated once.

No assignment is performed if the left-hand side is not truthy, due to
short-circuiting of the [logical AND](logical_and) operator. For
example, the following does not throw an error, despite `x` being
`const`:

 
 
[js]


```js
const x = 0;
x &&= 2;
```


Neither would the following trigger the setter:

 
 
[js]


```js
const x = {
  get value() {
    return 0;
  },
  set value(v) {
    console.log("Setter called");
  },
};

x.value &&= 2;
```


In fact, if `x` is not truthy, `y` is not evaluated at all.

 
 
[js]


```js
const x = 0;
x &&= console.log("y evaluated");
// Logs nothing
```




 
Examples
--------


 
### Using logical AND assignment 

 
 
 
[js]


```js
let x = 0;
let y = 1;

x &&= 0; // 0
x &&= 1; // 0
y &&= 1; // 1
y &&= 0; // 0
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-assignment-operators]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-assignment-operators)

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

`Logical_AND_assignment`

85

85

79

71

14

85

79

60

14

14.0

85

1.2

15.0.0

 
See also 
--------

 
-   [Logical AND (`&&`)](logical_and)
-   [Nullish coalescing operator (`??`)](nullish_coalescing)
-   [Bitwise AND assignment (`&=`)](bitwise_and_assignment)
-   [Truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
-   [Falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND_assignment>

