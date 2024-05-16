Boolean.prototype.valueOf()
===========================


The `valueOf()` method of [`Boolean`](../boolean) values returns the
primitive value of a [`Boolean`](../boolean) object.



Try it 
------






Syntax
------




[js]


```js
valueOf()
```





### Parameters


None.




### Return value 


The primitive value of the given [`Boolean`](../boolean) object.




Description
-----------


The `valueOf()` method of [`Boolean`](../boolean) returns the primitive
value of a `Boolean` object or literal `Boolean` as a Boolean data type.

This method is usually called internally by JavaScript and not
explicitly in code.




Examples
--------



### Using `valueOf()` 




[js]


```js
x = new Boolean();
myVar = x.valueOf(); // assigns false to myVar
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-boolean.prototype.valueof]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-boolean.prototype.valueof)

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

`valueOf`

1

12

1

4

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


-   [`Object.prototype.valueOf()`](../object/valueof)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/valueOf>

