Logical OR assignment (\|\|=)
=============================

 
The `||=` operator only evaluates the right operand and assigns to the
left if the left operand is
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x ||= y
```




 
Description
-----------

 
Logical OR assignment
[*short-circuits*](operator_precedence#short-circuiting), meaning that
`x ||= y` is equivalent to `x || (x = y)`, except that the expression
`x` is only evaluated once.

No assignment is performed if the left-hand side is not falsy, due to
short-circuiting of the [logical OR](logical_or) operator. For example,
the following does not throw an error, despite `x` being `const`:

 
 
[js]


```js
const x = 1;
x ||= 2;
```


Neither would the following trigger the setter:

 
 
[js]


```js
const x = {
  get value() {
    return 1;
  },
  set value(v) {
    console.log("Setter called");
  },
};

x.value ||= 2;
```


In fact, if `x` is not falsy, `y` is not evaluated at all.

 
 
[js]


```js
const x = 1;
x ||= console.log("y evaluated");
// Logs nothing
```




 
Examples
--------


 
### Setting default content 

 
If the \"lyrics\" element is empty, display a default value:

 
 
[js]


```js
document.getElementById("lyrics").textContent ||= "No lyrics.";
```


Here the short-circuit is especially beneficial, since the element will
not be updated unnecessarily and won\'t cause unwanted side-effects such
as additional parsing or rendering work, or loss of focus, etc.

Note: Pay attention to the value returned by the API you\'re checking
against. If an empty string is returned (a
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value),
`||=` must be used, so that \"No lyrics.\" is displayed instead of a
blank space. However, if the API returns [`null`](null) or
[`undefined`](../global_objects/undefined) in case of blank content,
[`??=`](nullish_coalescing_assignment) should be used instead.



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

`Logical_OR_assignment`

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

 
-   [Logical OR (`||`)](logical_or)
-   [Nullish coalescing operator (`??`)](nullish_coalescing)
-   [Bitwise OR assignment (`|=`)](bitwise_or_assignment)
-   [Truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
-   [Falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR_assignment>

