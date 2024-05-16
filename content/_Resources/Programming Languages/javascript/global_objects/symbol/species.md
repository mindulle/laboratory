Symbol.species
==============

 
The `Symbol.species` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@species`. Methods that create
copies of an object may look up this symbol on the object for the
constructor function to use when creating the copy.

 
**Warning:** The existence of `@@species` allows execution of arbitrary
code and may create security vulnerabilities. It also makes certain
optimizations much harder. Engine implementers are [investigating
whether to remove this
feature](https://github.com/tc39/proposal-rm-builtin-subclassing). Avoid
relying on it if possible.



 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@species`.

 
Property attributes of `Symbol.species`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
The `@@species` accessor property allows subclasses to override the
default constructor for objects. This specifies a protocol about how
instances should be copied. For example, when you use copying methods of
arrays, such as [`map()`](../array/map). the `map()` method uses
`instance.constructor[Symbol.species]` to get the constructor for
constructing the new array. For more information, see [subclassing
built-ins](../../classes/extends#subclassing_built-ins).

All built-in implementations of `@@species` return the `this` value,
which is the current instance\'s constructor. This allows copying
methods to create instances of derived classes rather than the base
class --- for example, `map()` will return an array of the same type as
the original array.



 
Examples
--------


 
### Using species 

 
You might want to return [`Array`](../array) objects in your derived
array class `MyArray`. For example, when using methods such as
[`map()`](../array/map) that return the default constructor, you want
these methods to return a parent `Array` object, instead of the
`MyArray` object. The `species` symbol lets you do this:

 
 
[js]


```js
class MyArray extends Array {
  // Overwrite species to the parent Array constructor
  static get [Symbol.species]() {
    return Array;
  }
}
const a = new MyArray(1, 2, 3);
const mapped = a.map((x) => x * x);

console.log(mapped instanceof MyArray); // false
console.log(mapped instanceof Array); // true
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.species]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.species)

  -------------------------------------------------------------------------------------------------------------


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

`species`

51

13

41

38

10

51

41

41

10

5.0

51

1.0

6.5.0

 
See also 
--------

 
-   [`Array[@@species]`](../array/@@species)
-   [`ArrayBuffer[@@species]`](../arraybuffer/@@species)
-   [`Map[@@species]`](../map/@@species)
-   [`Promise[@@species]`](../promise/@@species)
-   [`RegExp[@@species]`](../regexp/@@species)
-   [`Set[@@species]`](../set/@@species)
-   [`TypedArray[@@species]`](../typedarray/@@species)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/species>

