WeakSet() constructor
=====================

 
The `WeakSet()` constructor creates [`WeakSet`](../weakset) objects.


 
Syntax
------

 
 
 
[js]


```js
new WeakSet()
new WeakSet(iterable)
```


 
**Note:** `WeakSet()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`iterable`](#iterable) [Optional]

:   If an [iterable object](../../statements/for...of) is passed, all of
    its elements will be added to the new `WeakSet`. `null` is treated
    as `undefined`.



 
Examples
--------


 
### Using the WeakSet object 

 
 
 
[js]


```js
const ws = new WeakSet();
const foo = {};
const bar = {};

ws.add(foo);
ws.add(bar);

ws.has(foo); // true
ws.has(bar); // true

ws.delete(foo); // removes foo from the set
ws.has(foo); // false, foo has been removed
ws.has(bar); // true, bar is retained
```


Note that `foo !== bar`. While they are similar objects, *they are not
**the same object***. And so they are both added to the set.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakset-constructor]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakset-constructor)

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

`WeakSet`

36

12

34

23

9

36

34

24

9

3.0

37

1.0

0.12.0

`iterable_allowed`

38

12

34

25

9

38

34

25

9

3.0

38

1.0

0.12.0

`null_allowed`

36

12

37

23

9

36

37

24

9

3.0

37

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `WeakSet` in
    `core-js`](https://github.com/zloirock/core-js#weakset)
-   [`WeakSet`](../weakset)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/WeakSet>

