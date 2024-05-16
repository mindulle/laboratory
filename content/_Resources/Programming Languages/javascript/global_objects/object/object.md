Object() constructor
====================

 
The `Object()` constructor turns the input into an object. Its behavior
depends on the input\'s type.


 
Syntax
------

 
 
 
[js]


```js
new Object()
new Object(value)

Object()
Object(value)
```


 
**Note:** `Object()` can be called with or without
[`new`](../../operators/new), but sometimes with different effects. See
[Return value](#return_value).




 
### Parameters

 

[`value`](#value) [Optional]

:   Any value.



 
### Return value 

 
When the `Object()` constructor itself is called or constructed, its
return value is an object:

-   If the value is [`null`](../../operators/null) or
    [`undefined`](../undefined), it creates and returns an empty object.
-   If the value is an object already, it returns the value.
-   Otherwise, it returns an object of a type that corresponds to the
    given value. For example, passing a [`BigInt`](../bigint) primitive
    returns a `BigInt` wrapper object.

When `Object()` is constructed but
[`new.target`](../../operators/new.target) is not the `Object`
constructor itself, the behavior is slightly different --- it
initializes a new object with `new.target.prototype` as its prototype.
Any argument value is ignored. This may happen, for example, when
`Object()` is implicitly called via [`super()`](../../operators/super)
in the constructor of a class that [extends
`Object`](../../classes/extends#extending_object). In this case, even if
you pass a number to `super()`, the `this` value inside the constructor
does not become a [`Number`](../number) instance.



 
Examples
--------


 
### Creating a new Object 

 
 
 
[js]


```js
const o = new Object();
o.foo = 42;

console.log(o);
// { foo: 42 }
```




 
### Using Object given undefined and null types 

 
The following examples store an empty `Object` object in `o`:

 
 
[js]


```js
const o = new Object();
```


 
 
[js]


```js
const o = new Object(undefined);
```


 
 
[js]


```js
const o = new Object(null);
```




 
### Obtaining wrapper objects for BigInt and Symbol 

 
The [`BigInt()`](../bigint/bigint) and [`Symbol()`](../symbol/symbol)
constructors throw an error when called with `new`, to prevent the
common mistake of creating a wrapper object instead of the primitive
value. The only way to create a wrapper object for these types is to
call `Object()` with them:

 
 
[js]


```js
const numberObj = new Number(1);
console.log(typeof numberObj); // "object"

const bigintObj = Object(1n);
console.log(typeof bigintObj); // "object"

const symbolObj = Object(Symbol("foo"));
console.log(typeof symbolObj); // "object"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object-constructor]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object-constructor)

  ---------------------------------------------------------------------------------------------------------------------


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

`Object`

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

 
-   [Object initializer](../../operators/object_initializer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/Object>

