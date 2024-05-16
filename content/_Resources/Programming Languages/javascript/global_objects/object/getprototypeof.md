Object.getPrototypeOf()
=======================

 
The `Object.getPrototypeOf()` static method returns the prototype (i.e.
the value of the internal `[[Prototype]]` property) of the specified
object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.getPrototypeOf(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   The object whose prototype is to be returned.



 
### Return value 

 
The prototype of the given object, which may be
[`null`](../../operators/null).



 
Examples
--------


 
### Using getPrototypeOf 

 
 
 
[js]


```js
const proto = {};
const obj = Object.create(proto);
Object.getPrototypeOf(obj) === proto; // true
```




 
### Non-object coercion 

 
In ES5, it will throw a [`TypeError`](../typeerror) exception if the
`obj` parameter isn\'t an object. In ES2015, the parameter will be
coerced to an [`Object`](../object).

 
 
[js]


```js
Object.getPrototypeOf("foo");
// TypeError: "foo" is not an object (ES5 code)
Object.getPrototypeOf("foo");
// String.prototype                  (ES2015 code)
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.getprototypeof]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.getprototypeof)

  ---------------------------------------------------------------------------------------------------------------------------


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

`getPrototypeOf`

5

12

3.5

12.1

5

18

4

12.1

5

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Object.getPrototypeOf` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.prototype.isPrototypeOf()`](isprototypeof)
-   [`Object.setPrototypeOf()`](setprototypeof)
-   [`Object.prototype.__proto__`](proto)
-   [`Reflect.getPrototypeOf()`](../reflect/getprototypeof)
-   [Object.getPrototypeOf](https://johnresig.com/blog/objectgetprototypeof/)
    by John Resig (2008)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf>

