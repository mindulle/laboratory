WeakMap() constructor
=====================

 
The `WeakMap()` constructor creates [`WeakMap`](../weakmap) objects.


 
Syntax
------

 
 
 
[js]


```js
new WeakMap()
new WeakMap(iterable)
```


 
**Note:** `WeakMap()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`iterable`](#iterable)

:   An [`Array`](../array) or other iterable object that implements an
    [@\@iterator](../array/@@iterator) method that returns an iterator
    object that produces a two-element array-like object whose first
    element is a value that will be used as a `WeakMap` key and whose
    second element is the value to associate with that key. Each
    key-value pair will be added to the new `WeakMap`. null is treated
    as undefined.



 
Examples
--------


 
### Using WeakMap 

 
 
 
[js]


```js
const wm1 = new WeakMap();
const wm2 = new WeakMap();
const wm3 = new WeakMap();
const o1 = {};
const o2 = function () {};
const o3 = window;

wm1.set(o1, 37);
wm1.set(o2, "azerty");
wm2.set(o1, o2); // a value can be anything, including an object or a function
wm2.set(o3, undefined);
wm2.set(wm1, wm2); // keys and values can be any objects. Even WeakMaps!

wm1.get(o2); // "azerty"
wm2.get(o2); // undefined, because there is no key for o2 on wm2
wm2.get(o3); // undefined, because that is the set value

wm1.has(o2); // true
wm2.has(o2); // false
wm2.has(o3); // true (even if the value itself is 'undefined')

wm3.set(o1, 37);
wm3.get(o1); // 37

wm1.has(o1); // true
wm1.delete(o1);
wm1.has(o1); // false
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakmap-constructor]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakmap-constructor)

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

`WeakMap`

36

12

6

23

8

36

6

24

8

3.0

37

1.0

0.12.0

`iterable_allowed`

38

12

36

25

9

38

36

25

9

3.0

38

1.0

0.12.0

`new_required`

36

12

42

23

9

36

42

24

9

3.0

37

1.0

0.12.0

`null_allowed`

36

12

37

23

8

36

37

24

8

3.0

37

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `WeakMap` in
    `core-js`](https://github.com/zloirock/core-js#weakmap)
-   [`WeakMap` in the JavaScript
    guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections#weakmap_object)
-   [Hiding Implementation Details with ECMAScript 6
    WeakMaps](https://fitzgeraldnick.com/2014/01/13/hiding-implementation-details-with-e6-weakmaps.html)
-   [`Map`](../map)
-   [`Set`](../set)
-   [`WeakSet`](../weakset)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/WeakMap>

