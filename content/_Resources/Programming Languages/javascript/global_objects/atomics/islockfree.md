Atomics.isLockFree()
====================


The `Atomics.isLockFree()` static method is used to determine whether
the `Atomics` methods use locks or atomic hardware operations when
applied to typed arrays with the given element byte size. It returns
`false` if the given size is not one of the
[BYTES\_PER\_ELEMENT](../typedarray/bytes_per_element) property of
integer TypedArray types.



Try it 
------






Syntax
------




[js]


```js
Atomics.isLockFree(size)
```





### Parameters



[`size`](#size)

:   The size in bytes to check.




### Return value 


A `true` or `false` value indicating whether the operation is lock free.




Examples
--------



### Using isLockFree 




[js]


```js
Atomics.isLockFree(1); // true
Atomics.isLockFree(2); // true
Atomics.isLockFree(3); // false
Atomics.isLockFree(4); // true
Atomics.isLockFree(5); // false
Atomics.isLockFree(6); // false
Atomics.isLockFree(7); // false
Atomics.isLockFree(8); // true
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-atomics.islockfree]](https://tc39.es/ecma262/multipage/structured-data.html#sec-atomics.islockfree)

  -----------------------------------------------------------------------------------------------------------------


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

`isLockFree`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0


See also 
--------


-   [`Atomics`](../atomics)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics/isLockFree>

