Set.prototype.symmetricDifference()
===================================

[Limited availability]
---------------------------------

 
This feature is not Baseline because it does not work in some of the
most widely-used browsers.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FSet%2FsymmetricDifference&level=not)


 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `symmetricDifference()` method of [`Set`](../set) instances takes a
set and returns a new set containing elements which are in either this
set or the given set, but not in both.


 
Syntax
------

 
 
 
[js]


```js
symmetricDifference(other)
```




 
### Parameters

 

[`other`](#other)

:   A [`Set`](../set) object, or [set-like](../set#set-like_objects)
    object.



 
### Return value 

 
A new [`Set`](../set) object containing elements which are in either
this set or the `other` set, but not in both.



 
Description
-----------

 
In mathematical notation, *symmetric difference* is defined as:

$$A \ominus B = (A \smallsetminus B) \cup (B \smallsetminus A)$$

And using Venn diagram:




`symmetricDifference()` accepts [set-like](../set#set-like_objects)
objects as the `other` parameter. It requires
[`this`](../../operators/this) to be an actual [`Set`](../set) instance,
because it directly retrieves the underlying data stored in `this`
without invoking any user code. Then, it iterates over `other` by
calling its `keys()` method, and constructs a new set with all elements
in `this` that are not seen in `other`, and all elements in `other` that
are not seen in `this`.

The order of elements in the returned set is first those in `this`
followed by those in `other`.



 
Examples
--------


 
### Using symmetricDifference() 

 
The following example computes the symmetric difference between the set
of even numbers (\<10) and the set of perfect squares (\<10). The result
is the set of numbers that are either even or a perfect square, but not
both.

 
 
[js]


```js
const evens = new Set([2, 4, 6, 8]);
const squares = new Set([1, 4, 9]);
console.log(evens.symmetricDifference(squares)); // Set(5) { 1, 2, 6, 8, 9 }
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------
  [Set methods\
  [\#
  sec-set.prototype.symmetricDifference]](https://tc39.es/proposal-set-methods/#sec-set.prototype.symmetricDifference)

  ------------------------------------------------------------------------------------------------------------------------------


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

`symmetricDifference`

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

 
-   [Polyfill of `Set.prototype.symmetricDifference` in
    `core-js`](https://github.com/zloirock/core-js#new-set-methods)
-   [`Set.prototype.difference()`](difference)
-   [`Set.prototype.intersection()`](intersection)
-   [`Set.prototype.isDisjointFrom()`](isdisjointfrom)
-   [`Set.prototype.isSubsetOf()`](issubsetof)
-   [`Set.prototype.isSupersetOf()`](issupersetof)
-   [`Set.prototype.union()`](union)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/symmetricDifference>

