Intl.Collator.prototype.compare()
=================================

 
The `compare()` method of [`Intl.Collator`](../collator) instances
compares two strings according to the sort order of this collator
object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
compare(string1, string2)
```




 
### Parameters

 

[`string1`](#string1), `string2`

:   The strings to compare against each other.



 
### Return value 

 
A number indicating how `string1` and `string2` compare to each other
according to the sort order of this [`Intl.Collator`](../collator)
object:

-   A negative value if `string1` comes before `string2`;
-   A positive value if `string1` comes after `string2`;
-   0 if they are considered equal.



 
Examples
--------


 
### Using compare for array sort 

 
Use the `compare` function for sorting arrays. Note that the function is
bound to the collator from which it was obtained, so it can be passed
directly to [`Array.prototype.sort()`](../../array/sort).

 
 
[js]


```js
const a = ["Offenbach", "Österreich", "Odenwald"];
const collator = new Intl.Collator("de-u-co-phonebk");
a.sort(collator.compare);
console.log(a.join(", ")); // "Odenwald, Österreich, Offenbach"
```




 
### Using compare for array search 

 
Use the `compare` function for finding matching strings in arrays:

 
 
[js]


```js
const a = ["Congrès", "congres", "Assemblée", "poisson"];
const collator = new Intl.Collator("fr", {
  usage: "search",
  sensitivity: "base",
});
const s = "congres";
const matches = a.filter((v) => collator.compare(v, s) === 0);
console.log(matches.join(", ")); // "Congrès, congres"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.collator.prototype.compare]](https://tc39.es/ecma402/#sec-intl.collator.prototype.compare)

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

`compare`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `Collator()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/Collator)
for more details.

 
See also 
--------

 
-   [`Intl.Collator`](../collator)
-   [`String.prototype.localeCompare()`](../../string/localecompare)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/compare>

