String.prototype.toString()
===========================

 
The `toString()` method of [`String`](../string) values returns this
string value.


 
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

 
A string representing the specified string value.



 
Description
-----------

 
The [`String`](../string) object overrides the `toString` method of
[`Object`](../object); it does not inherit
[`Object.prototype.toString()`](../object/tostring). For `String`
values, the `toString` method returns the string itself (if it\'s a
primitive) or the string that the `String` object wraps. It has the
exact same implementation as [`String.prototype.valueOf()`](valueof).

The `toString()` method requires its `this` value to be a `String`
primitive or wrapper object. It throws a [`TypeError`](../typeerror) for
other `this` values without attempting to coerce them to string values.

Because `String` doesn\'t have a
[`[@@toPrimitive]()`](../symbol/toprimitive) method, JavaScript calls
the `toString()` method automatically when a `String` *object* is used
in a context expecting a string, such as in a [template
literal](../../template_literals). However, String *primitive* values do
not consult the `toString()` method to be [coerced to
strings](../string#string_coercion) --- since they are already strings,
no conversion is performed.

 
 
[js]


```js
String.prototype.toString = () => "Overridden";
console.log(`${"foo"}`); // "foo"
console.log(`${new String("foo")}`); // "Overridden"
```




 
Examples
--------


 
### Using toString() 

 
The following example displays the string value of a
[`String`](../string) object:

 
 
[js]


```js
const x = new String("Hello world");

console.log(x.toString()); // "Hello world"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.tostring]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.tostring)

  -------------------------------------------------------------------------------------------------------------------------------


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

3

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

 
-   [`String.prototype.valueOf()`](valueof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toString>

