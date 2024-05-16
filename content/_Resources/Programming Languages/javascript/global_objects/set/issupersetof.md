Set.prototype.isSupersetOf()
============================

[Limited availability]
---------------------------------

 
This feature is not Baseline because it does not work in some of the
most widely-used browsers.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FSet%2FisSupersetOf&level=not)


 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `isSupersetOf()` method of [`Set`](../set) instances takes a set and
returns a boolean indicating if all elements of the given set are in
this set.


 
Syntax
------

 
 
 
[js]


```js
isSupersetOf(other)
```




 
### Parameters

 

[`other`](#other)

:   A [`Set`](../set) object, or [set-like](../set#set-like_objects)
    object.



 
### Return value 

 
`true` if all elements in the `other` set are also in this set, and
`false` otherwise.



 
Description
-----------

 
In mathematical notation, *superset* is defined as:

$$A \supseteq B\Leftrightarrow\forall x \in B,\, x \in A$$

And using Venn diagram:




 
**Note:** The *superset* relationship is not *proper superset*, which
means `isSupersetOf()` returns `true` if `this` and `other` contain the
same elements.


`isSupersetOf()` accepts [set-like](../set#set-like_objects) objects as
the `other` parameter. It requires [`this`](../../operators/this) to be
an actual [`Set`](../set) instance, because it directly retrieves the
underlying data stored in `this` without invoking any user code. Then,
its behavior depends on the sizes of `this` and `other`:

-   If there are fewer elements in `this` than `other.size`, then it
    directly returns `false`.
-   Otherwise, it iterates over `other` by calling its `keys()` method,
    and if any element in `other` is not present in `this`, it returns
    `false` (and closes the `keys()` iterator by calling its `return()`
    method). Otherwise, it returns `true`.



 
Examples
--------


 
### Using isSupersetOf() 

 
The set of even numbers (\<20) is a superset of multiples of 4 (\<20):

 
 
[js]


```js
const evens = new Set([2, 4, 6, 8, 10, 12, 14, 16, 18]);
const fours = new Set([4, 8, 12, 16]);
console.log(evens.isSupersetOf(fours)); // true
```


The set of all odd numbers (\<20) is not a superset of prime numbers
(\<20), because 2 is prime but not odd:

 
 
[js]


```js
const primes = new Set([2, 3, 5, 7, 11, 13, 17, 19]);
const odds = new Set([3, 5, 7, 9, 11, 13, 15, 17, 19]);
console.log(odds.isSupersetOf(primes)); // false
```


Equivalent sets are supersets of each other:

 
 
[js]


```js
const set1 = new Set([1, 2, 3]);
const set2 = new Set([1, 2, 3]);
console.log(set1.isSupersetOf(set2)); // true
console.log(set2.isSupersetOf(set1)); // true
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------
  [Set methods\
  [\#
  sec-set.prototype.isSupersetOf]](https://tc39.es/proposal-set-methods/#sec-set.prototype.isSupersetOf)

  ----------------------------------------------------------------------------------------------------------------


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

`isSupersetOf`

No

No

preview

No

17

No

No

No

17

No

No

No

No

 
See also 
--------

 
-   [Polyfill of `Set.prototype.isSupersetOf` in
    `core-js`](https://github.com/zloirock/core-js#new-set-methods)
-   [`Set.prototype.difference()`](difference)
-   [`Set.prototype.intersection()`](intersection)
-   [`Set.prototype.isDisjointFrom()`](isdisjointfrom)
-   [`Set.prototype.isSubsetOf()`](issubsetof)
-   [`Set.prototype.symmetricDifference()`](symmetricdifference)
-   [`Set.prototype.union()`](union)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/isSupersetOf>

