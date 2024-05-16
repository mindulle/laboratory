Object.prototype.toLocaleString()
=================================

 
The `toLocaleString()` method of [`Object`](../object) instances returns
a string representing this object. This method is meant to be overridden
by derived objects for locale-specific purposes.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toLocaleString()
```




 
### Parameters

 
None. However, all objects that override this method are expected to
accept at most two parameters, corresponding to `locales` and `options`,
such as [`Date.prototype.toLocaleString`](../date/tolocalestring). The
parameter positions should not be used for any other purpose.



 
### Return value 

 
The return value of calling `this.toString()`.



 
Description
-----------

 
All objects that inherit from `Object.prototype` (that is, all except
[`null`-prototype objects](../object#null-prototype_objects)) inherit
the `toLocaleString()` method. [`Object`](../object)\'s `toLocaleString`
returns the result of calling [`this.toString()`](tostring).

This function is provided to give objects a generic `toLocaleString`
method, even though not all may use it. In the core language, these
built-in objects override `toLocaleString` to provide locale-specific
formatting:

-   [`Array`](../array):
    [`Array.prototype.toLocaleString()`](../array/tolocalestring)
-   [`Number`](../number):
    [`Number.prototype.toLocaleString()`](../number/tolocalestring)
-   [`Date`](../date):
    [`Date.prototype.toLocaleString()`](../date/tolocalestring)
-   [`TypedArray`](../typedarray):
    [`TypedArray.prototype.toLocaleString()`](../typedarray/tolocalestring)
-   [`BigInt`](../bigint):
    [`BigInt.prototype.toLocaleString()`](../bigint/tolocalestring)



 
Examples
--------


 
### Using the base toLocaleString() method 

 
The base `toLocaleString()` method simply calls `toString()`.

 
 
[js]


```js
const obj = {
  toString() {
    return "My Object";
  },
};
console.log(obj.toLocaleString()); // "My Object"
```




 
### Array toLocaleString() override 

 
[`Array.prototype.toLocaleString()`](../array/tolocalestring) is used to
print array values as a string by invoking each element\'s
`toLocaleString()` method and joining the results with a locale-specific
separator. For example:

 
 
[js]


```js
const testArray = [4, 7, 10];

const euroPrices = testArray.toLocaleString("fr", {
  style: "currency",
  currency: "EUR",
});
// "4,00 €,7,00 €,10,00 €"
```




 
### Date toLocaleString() override 

 
[`Date.prototype.toLocaleString()`](../date/tolocalestring) is used to
print out date displays more suitable for specific locales. For example:

 
 
[js]


```js
const testDate = new Date();
// "Fri May 29 2020 18:04:24 GMT+0100 (British Summer Time)"

const deDate = testDate.toLocaleString("de");
// "29.5.2020, 18:04:24"

const frDate = testDate.toLocaleString("fr");
// "29/05/2020, 18:04:24"
```




 
### Number toLocaleString() override 

 
[`Number.prototype.toLocaleString()`](../number/tolocalestring) is used
to print out number displays more suitable for specific locales, e.g.
with the correct separators. For example:

 
 
[js]


```js
const testNumber = 2901234564;
// "2901234564"

const deNumber = testNumber.toLocaleString("de");
// "2.901.234.564"

const frNumber = testNumber.toLocaleString("fr");
// "2 901 234 564"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.prototype.tolocalestring]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.prototype.tolocalestring)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

`toLocaleString`

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

 
-   [`Object.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toLocaleString>

