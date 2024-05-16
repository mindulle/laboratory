Intl.supportedValuesOf()
========================

 
The `Intl.supportedValuesOf()` static method returns an array containing
the supported calendar, collation, currency, numbering systems, or unit
values supported by the implementation.

Duplicates are omitted and the array is sorted in ascending
lexicographical order (or more precisely, using
[`Array.prototype.sort()`](../array/sort) with an `undefined` compare
function).

The method can be used to feature-test whether values are supported in a
particular implementation and download a polyfill only if necessary. It
can also be used to build UIs that allow users to select their preferred
localized values, for example when the UI is created from WebGL or
server-side.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Intl.supportedValuesOf(key)
```




 
### Parameters

 

[`key`](#key)

:   A key string indicating the category of values to be returned. This
    is one of: `"calendar"`, `"collation"`, `"currency"`,
    `"numberingSystem"`, `"timeZone"`, `"unit"`.



 
### Return value 

 
A sorted array of unique string values indicating the values supported
by the implementation for the given key.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if an unsupported key was passed as a parameter.



 
Examples
--------


 
### Feature testing 

 
You can check that the method is supported by comparing to `undefined`:

 
 
[js]


```js
if (typeof Intl.supportedValuesOf !== "undefined") {
  // method is supported
}
```




 
### Get all values for key 

 
To get the supported values for calendar you call the method with the
key `"calendar"`. You can then iterate through the returned array as
shown below:

 
 
[js]


```js
Intl.supportedValuesOf("calendar").forEach((calendar) => {
  // "buddhist", "chinese", "coptic", "dangi", etc.
});
```


 
**Note:** The array returned for calendar values will always include the
value \"gregory\" (gregorian).


The other values are all obtained in the same way:

 
 
[js]


```js
Intl.supportedValuesOf("collation").forEach((collation) => {
  // "compat", "dict", "emoji", etc.
});

Intl.supportedValuesOf("currency").forEach((currency) => {
  // "ADP", "AED", "AFA", "AFN", "ALK", "ALL", "AMD", etc.
});

Intl.supportedValuesOf("numberingSystem").forEach((numberingSystem) => {
  // "adlm", "ahom", "arab", "arabext", "bali", etc.
});

Intl.supportedValuesOf("timeZone").forEach((timeZone) => {
  // "Africa/Abidjan", "Africa/Accra", "Africa/Addis_Ababa", "Africa/Algiers", etc.
});

Intl.supportedValuesOf("unit").forEach((unit) => {
  // "acre", "bit", "byte", "celsius", "centimeter", etc.
});
```




 
### Invalid key throws RangeError 

 
 
 
[js]


```js
try {
  Intl.supportedValuesOf("someInvalidKey");
} catch (err) {
  //Error: RangeError: invalid key: "someInvalidKey"
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.supportedvaluesof]](https://tc39.es/ecma402/#sec-intl.supportedvaluesof)

  -------------------------------------------------------------------------------------------


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

`supportedValuesOf`

99

99

93

85

15.4

99

93

68

15.4

18.0

99

1.19

18.0.0

 
See also 
--------

 
-   [Polyfill of `Intl.supportedValuesOf` in
    FormatJS](https://github.com/formatjs/formatjs/tree/main/packages/intl-enumerator)
-   [`Intl`](../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/supportedValuesOf>

