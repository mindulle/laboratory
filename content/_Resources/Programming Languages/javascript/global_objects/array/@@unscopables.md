Array.prototype\[@\@unscopables\]
=================================


The `@@unscopables` data property of `Array.prototype` is shared by all
[`Array`](../array) instances. It contains property names that were not
included in the ECMAScript standard prior to the ES2015 version and that
are ignored for [`with`](../../statements/with) statement-binding
purposes.



Value
-----


A [`null`-prototype object](../object#null-prototype_objects) with
property names given below and their values set to `true`.


Property attributes of `Array.prototype[@@unscopables]`




Writable

no

Enumerable

no

Configurable

yes


Description
-----------


The default `Array` properties that are ignored for `with`
statement-binding purposes are:

-   [`at()`](at)
-   [`copyWithin()`](copywithin)
-   [`entries()`](entries)
-   [`fill()`](fill)
-   [`find()`](find)
-   [`findIndex()`](findindex)
-   [`findLast()`](findlast)
-   [`findLastIndex()`](findlastindex)
-   [`flat()`](_Resources/Programming%20Languages/javascript/global_objects/array/flat.md)
-   [`flatMap()`](flatmap)
-   [`includes()`](includes)
-   [`keys()`](keys)
-   [`toReversed()`](toreversed)
-   [`toSorted()`](tosorted)
-   [`toSpliced()`](tospliced)
-   [`values()`](values)

`Array.prototype[@@unscopables]` is an empty object only containing all
the above property names with the value `true`. Its [prototype is
`null`](../object#null-prototype_objects), so `Object.prototype`
properties like [`toString`](../object/tostring) won\'t accidentally be
made unscopable, and a `toString()` within the `with` statement will
continue to be called on the array.

See [`Symbol.unscopables`](../symbol/unscopables) for how to set
unscopable properties for your own objects.




Examples
--------


Imagine the `keys.push('something')` call below is in code that was
written prior to ECMAScript 2015.



[js]


```js
var keys = [];

with (Array.prototype) {
  keys.push("something");
}
```


When ECMAScript 2015 introduced the [`Array.prototype.keys()`](keys)
method, if the `@@unscopables` data property had not also been
introduced, that `keys.push('something')` call would break --- because
the JavaScript runtime would have interpreted `keys` as being the
[`Array.prototype.keys()`](keys) method, rather than the `keys` array
defined in the example code.

So the `@@unscopables` data property for `Array.prototype` causes the
`Array` properties introduced in ECMAScript 2015 to be ignored for
`with` statement-binding purposes --- allowing code that was written
prior to ECMAScript 2015 to continue working as expected, rather than
breaking.



Specifications
--------------


  --------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype-@\@unscopables]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype-@@unscopables)

  --------------------------------------------------------------------------------------------------------------------------------------------


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

`@@unscopables`

38

12

48

25

10

38

48

25

10

3.0

38

1.0

0.12.0


See also 
--------


-   [Polyfill of `Array.prototype[@@unscopables]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`with`](../../statements/with)
-   [`Symbol.unscopables`](../symbol/unscopables)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@unscopables>

