Set.prototype.isSubsetOf()
==========================

[Limited availability]
---------------------------------

 
This feature is not Baseline because it does not work in some of the
most widely-used browsers.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FSet%2FisSubsetOf&level=not)


 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `isSubsetOf()` method of [`Set`](../set) instances takes a set and
returns a boolean indicating if all elements of this set are in the
given set.


 
Syntax
------

 
 
 
[js]


```js
isSubsetOf(other)
```




 
### Parameters

 

[`other`](#other)

:   A [`Set`](../set) object, or [set-like](../set#set-like_objects)
    object.



 
### Return value 

 
`true` if all elements in this set are also in the `other` set, and
`false` otherwise.



 
Description
-----------

 
In mathematical notation, *subset* is defined as:

$$A \subseteq B\Leftrightarrow\forall x \in A,\, x \in B$$

And using Venn diagram:




 
**Note:** The *subset* relationship is not *proper subset*, which means
`isSubsetOf()` returns `true` if `this` and `other` contain the same
elements.


`isSubsetOf()` accepts [set-like](../set#set-like_objects) objects as
the `other` parameter. It requires [`this`](../../operators/this) to be
an actual [`Set`](../set) instance, because it directly retrieves the
underlying data stored in `this` without invoking any user code. Then,
its behavior depends on the sizes of `this` and `other`:

-   If there are more elements in `this` than `other.size`, then it
    directly returns `false`.
-   Otherwise, it iterates over the elements in `this`, and returns
    `false` if any element `e` in `this` causes `other.has(e)` to return
    a [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value. Otherwise, it returns `true`.



 
Examples
--------


 
### Using isSubsetOf() 

 
The set of multiples of 4 (\<20) is a subset of even numbers (\<20):

 
 
[js]


```js
const fours = new Set([4, 8, 12, 16]);
const evens = new Set([2, 4, 6, 8, 10, 12, 14, 16, 18]);
console.log(fours.isSubsetOf(evens)); // true
```


The set of prime numbers (\<20) is not a subset of all odd numbers
(\<20), because 2 is prime but not odd:

 
 
[js]


```js
const primes = new Set([2, 3, 5, 7, 11, 13, 17, 19]);
const odds = new Set([3, 5, 7, 9, 11, 13, 15, 17, 19]);
console.log(primes.isSubsetOf(odds)); // false
```


Equivalent sets are subsets of each other:

 
 
[js]


```js
const set1 = new Set([1, 2, 3]);
const set2 = new Set([1, 2, 3]);
console.log(set1.isSubsetOf(set2)); // true
console.log(set2.isSubsetOf(set1)); // true
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------
  [Set methods\
  [\#
  sec-set.prototype.isSubsetOf]](https://tc39.es/proposal-set-methods/#sec-set.prototype.isSubsetOf)

  ------------------------------------------------------------------------------------------------------------


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

`isSubsetOf`

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

 
-   [Polyfill of `Set.prototype.isSubsetOf` in
    `core-js`](https://github.com/zloirock/core-js#new-set-methods)
-   [`Set.prototype.difference()`](difference)
-   [`Set.prototype.intersection()`](intersection)
-   [`Set.prototype.isDisjointFrom()`](isdisjointfrom)
-   [`Set.prototype.isSupersetOf()`](issupersetof)
-   [`Set.prototype.symmetricDifference()`](symmetricdifference)
-   [`Set.prototype.union()`](union)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/isSubsetOf>

