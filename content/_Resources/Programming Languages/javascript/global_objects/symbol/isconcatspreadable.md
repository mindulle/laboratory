Symbol.isConcatSpreadable
=========================

 
The `Symbol.isConcatSpreadable` static data property represents the
[well-known symbol](../symbol#well-known_symbols)
`@@isConcatSpreadable`. The
[`Array.prototype.concat()`](../array/concat) method looks up this
symbol on each object being concatenated to determine if it should be
treated as an array-like object and flattened to its array elements.


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@isConcatSpreadable`.

 
Property attributes of `Symbol.isConcatSpreadable`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
The `@@isConcatSpreadable` symbol (`Symbol.isConcatSpreadable`) can be
defined as an own or inherited property and its value is a boolean. It
can control behavior for arrays and array-like objects:

-   For array objects, the default behavior is to spread (flatten)
    elements. `Symbol.isConcatSpreadable` can avoid flattening in these
    cases.
-   For array-like objects, the default behavior is no spreading or
    flattening. `Symbol.isConcatSpreadable` can force flattening in
    these cases.



 
Examples
--------


 
### Arrays

 
By default, [`Array.prototype.concat()`](../array/concat) spreads
(flattens) arrays into its result:

 
 
[js]


```js
const alpha = ["a", "b", "c"];
const numeric = [1, 2, 3];

const alphaNumeric = alpha.concat(numeric);

console.log(alphaNumeric); // Result: ['a', 'b', 'c', 1, 2, 3]
```


When setting `Symbol.isConcatSpreadable` to `false`, you can disable the
default behavior:

 
 
[js]


```js
const alpha = ["a", "b", "c"];
const numeric = [1, 2, 3];

numeric[Symbol.isConcatSpreadable] = false;
const alphaNumeric = alpha.concat(numeric);

console.log(alphaNumeric); // Result: ['a', 'b', 'c', [1, 2, 3] ]
```




 
### Array-like objects 

 
For array-like objects, the default is to not spread.
`Symbol.isConcatSpreadable` needs to be set to `true` in order to get a
flattened array:

 
 
[js]


```js
const x = [1, 2, 3];

const fakeArray = {
  [Symbol.isConcatSpreadable]: true,
  length: 2,
  0: "hello",
  1: "world",
};

x.concat(fakeArray); // [1, 2, 3, "hello", "world"]
```


 
**Note:** The `length` property is used to control the number of object
properties to be added. In the above example, `length:2` indicates two
properties has to be added.




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.isconcatspreadable]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.isconcatspreadable)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`isConcatSpreadable`

48

15

48

35

10

48

48

35

10

5.0

48

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `Symbol.isConcatSpreadable` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Array.prototype.concat()`](../array/concat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/isConcatSpreadable>

