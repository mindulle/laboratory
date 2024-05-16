Nullish coalescing assignment (??=)
===================================

 
The `??=` operator, also known as the **logical nullish assignment**
operator, only evaluates the right operand and assigns to the left if
the left operand is
[nullish](https://developer.mozilla.org/en-US/docs/Glossary/Nullish)
(`null` or `undefined`).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x ??= y
```




 
Description
-----------

 
Nullish coalescing assignment
[*short-circuits*](operator_precedence#short-circuiting), meaning that
`x ??= y` is equivalent to `x ?? (x = y)`, except that the expression
`x` is only evaluated once.

No assignment is performed if the left-hand side is not nullish, due to
short-circuiting of the [nullish coalescing](nullish_coalescing)
operator. For example, the following does not throw an error, despite
`x` being `const`:

 
 
[js]


```js
const x = 1;
x ??= 2;
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

x.value ??= 2;
```


In fact, if `x` is not nullish, `y` is not evaluated at all.

 
 
[js]


```js
const x = 1;
x ??= console.log("y evaluated");
// Logs nothing
```




 
Examples
--------


 
### Using nullish coalescing assignment 

 
You can use the nullish coalescing assignment operator to apply default
values to object properties. Compared to using destructuring and
[default values](destructuring_assignment#default_value), `??=` also
applies the default value if the property has value `null`.

 
 
[js]


```js
function config(options) {
  options.duration ??= 100;
  options.speed ??= 25;
  return options;
}

config({ duration: 125 }); // { duration: 125, speed: 25 }
config({}); // { duration: 100, speed: 25 }
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

`Nullish_coalescing_assignment`

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

 
-   [Nullish coalescing operator (`??`)](nullish_coalescing)
-   [Nullish](https://developer.mozilla.org/en-US/docs/Glossary/Nullish)
-   [Truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
-   [Falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_assignment>

