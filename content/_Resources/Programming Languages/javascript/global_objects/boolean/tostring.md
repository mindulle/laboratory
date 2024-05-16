Boolean.prototype.toString()
============================


The `toString()` method of [`Boolean`](../boolean) values returns a
string representing the specified boolean value.



Try it 
------






Syntax
------




[js]


```js
toString()
```





### Parameters


None.




### Return value 


A string representing the specified boolean value.




Description
-----------


The [`Boolean`](../boolean) object overrides the `toString` method of
[`Object`](../object); it does not inherit
[`Object.prototype.toString()`](../object/tostring). For `Boolean`
values, the `toString` method returns a string representation of the
boolean value, which is either `"true"` or `"false"`.

The `toString()` method requires its `this` value to be a `Boolean`
primitive or wrapper object. It throws a [`TypeError`](../typeerror) for
other `this` values without attempting to coerce them to boolean values.

Because `Boolean` doesn\'t have a
[`[@@toPrimitive]()`](../symbol/toprimitive) method, JavaScript calls
the `toString()` method automatically when a `Boolean` *object* is used
in a context expecting a string, such as in a [template
literal](../../template_literals). However, boolean *primitive* values
do not consult the `toString()` method to be [coerced to
strings](../string#string_coercion) --- rather, they are directly
converted using the same algorithm as the initial `toString()`
implementation.



[js]


```js
Boolean.prototype.toString = () => "Overridden";
console.log(`${true}`); // "true"
console.log(`${new Boolean(true)}`); // "Overridden"
```





Examples
--------



### Using toString() 




[js]


```js
const flag = new Boolean(true);
console.log(flag.toString()); // "true"
console.log(false.toString()); // "false"
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-boolean.prototype.tostring]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-boolean.prototype.tostring)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`toString`

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


-   [`Object.prototype.toString()`](../object/tostring)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/toString>

