Set() constructor
=================

 
The `Set()` constructor creates [`Set`](../set) objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Set()
new Set(iterable)
```


 
**Note:** `Set()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`iterable`](#iterable) [Optional]

:   If an [iterable object](../../statements/for...of) is passed, all of
    its elements will be added to the new `Set`.

    If you don\'t specify this parameter, or its value is `null`, the
    new `Set` is empty.



 
### Return value 

 
A new `Set` object.



 
Examples
--------


 
### Using the `Set` object 

 
 
 
[js]


```js
const mySet = new Set();

mySet.add(1); // Set [ 1 ]
mySet.add(5); // Set [ 1, 5 ]
mySet.add(5); // Set [ 1, 5 ]
mySet.add("some text"); // Set [ 1, 5, 'some text' ]
const o = { a: 1, b: 2 };
mySet.add(o);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set-constructor]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set-constructor)

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

`Set`

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

 
-   [Polyfill of `Set` in
    `core-js`](https://github.com/zloirock/core-js#set)
-   [`Set`](../set)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/Set>

