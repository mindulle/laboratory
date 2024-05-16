Map.prototype.forEach()
=======================

 
The `forEach()` method of [`Map`](../map) instances executes a provided
function once per each key/value pair in this map, in insertion order.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
forEach(callbackFn)
forEach(callbackFn, thisArg)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each entry in the map. The function is
    called with the following arguments:

    [`value`](#value)

    :   Value of each iteration.

    [`key`](#key)

    :   Key of each iteration.

    [`map`](#map)

    :   The map being iterated.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`.



 
### Return value 

 
None ([`undefined`](../undefined)).



 
Description
-----------

 
The `forEach` method executes the provided `callback` once for each key
of the map which actually exist. It is not invoked for keys which have
been deleted. However, it is executed for values which are present but
have the value `undefined`.

`callback` is invoked with **three arguments**:

-   the entry\'s `value`
-   the entry\'s `key`
-   the `Map` being traversed

If a `thisArg` parameter is provided to `forEach`, it will be passed to
`callback` when invoked, for use as its `this` value. Otherwise, the
value `undefined` will be passed for use as its `this` value. The `this`
value ultimately observable by `callback` is determined according to
[the usual rules for determining the `this` seen by a
function](../../operators/this).

Each value is visited once, except in the case when it was deleted and
re-added before `forEach` has finished. `callback` is not invoked for
values deleted before being visited. New values added before `forEach`
has finished will be visited.



 
Examples
--------


 
### Printing the contents of a Map object 

 
The following code logs a line for each element in an `Map` object:

 
 
[js]


```js
function logMapElements(value, key, map) {
  console.log(`map.get('${key}') = ${value}`);
}
new Map([
  ["foo", 3],
  ["bar", {}],
  ["baz", undefined],
]).forEach(logMapElements);
// Logs:
// "map.get('foo') = 3"
// "map.get('bar') = [object Object]"
// "map.get('baz') = undefined"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.foreach]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.foreach)

  -------------------------------------------------------------------------------------------------------------------------


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

`forEach`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Array.prototype.forEach()`](../array/foreach)
-   [`Set.prototype.forEach()`](../set/foreach)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/forEach>

