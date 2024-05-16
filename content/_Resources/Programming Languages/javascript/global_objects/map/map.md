Map() constructor
=================

 
The `Map()` constructor creates [`Map`](../map) objects.


 
Syntax
------

 
 
 
[js]


```js
new Map()
new Map(iterable)
```


 
**Note:** `Map()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`iterable`](#iterable) [Optional]

:   An [`Array`](../array) or other
    [iterable](../../iteration_protocols) object whose elements are
    key-value pairs. (For example, arrays with two elements, such as
    `[[ 1, 'one' ],[ 2, 'two' ]]`.) Each key-value pair is added to the
    new `Map`.



 
Examples
--------


 
### Creating a new Map 

 
 
 
[js]


```js
const myMap = new Map([
  [1, "one"],
  [2, "two"],
  [3, "three"],
]);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map-constructor]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map-constructor)

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

`Map`

38

12

13

25

8

38

14

25

8

3.0

38

1.0

0.12.0

`iterable_allowed`

38

12

13

25

9

38

14

25

9

3.0

38

1.0

0.12.0

`new_required`

38

12

42

25

9

38

42

25

9

3.0

38

1.0

0.12.0

`null_allowed`

38

12

37

25

9

38

37

25

9

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill for `Map` in
    `core-js`](https://github.com/zloirock/core-js#map)
-   [`Set`](../set)
-   [`WeakMap`](../weakmap)
-   [`WeakSet`](../weakset)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/Map>

