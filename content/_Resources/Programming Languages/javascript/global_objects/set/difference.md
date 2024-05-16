Set.prototype.difference()
==========================

[Limited availability]
---------------------------------

 
This feature is not Baseline because it does not work in some of the
most widely-used browsers.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FSet%2Fdifference&level=not)


 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `difference()` method of [`Set`](../set) instances takes a set and
returns a new set containing elements in this set but not in the given
set.


 
Syntax
------

 
 
 
[js]


```js
difference(other)
```




 
### Parameters

 

[`other`](#other)

:   A [`Set`](../set) object, or [set-like](../set#set-like_objects)
    object.



 
### Return value 

 
A new [`Set`](../set) object containing elements in this set but not in
the `other` set.



 
Description
-----------

 
In mathematical notation, *difference* is defined as:

$$A \smallsetminus B = \{ x \in A \mid x \notin B\}$$

And using Venn diagram:




`difference()` accepts [set-like](../set#set-like_objects) objects as
the `other` parameter. It requires [`this`](../../operators/this) to be
an actual [`Set`](../set) instance, because it directly retrieves the
underlying data stored in `this` without invoking any user code. Then,
its behavior depends on the sizes of `this` and `other`:

-   If there are more elements in `this` than `other.size`, then it
    iterates over `other` by calling its `keys()` method, and constructs
    a new set with all elements in `this` that are not seen in `other`.
-   Otherwise, it iterates over the elements in `this`, and constructs a
    new set with all elements `e` in `this` that cause `other.has(e)` to
    return a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value.

The order of elements in the returned set is the same as in `this`.



 
Examples
--------


 
### Using difference() 

 
The following example computes the difference between the set of odd
numbers (\<10) and the set of perfect squares (\<10). The result is the
set of odd numbers that are not perfect squares.

 
 
[js]


```js
const odds = new Set([1, 3, 5, 7, 9]);
const squares = new Set([1, 4, 9]);
console.log(odds.difference(squares)); // Set(3) { 3, 5, 7 }
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------
  [Set methods\
  [\#
  sec-set.prototype.difference]](https://tc39.es/proposal-set-methods/#sec-set.prototype.difference)

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

`difference`

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

 
-   [Polyfill of `Set.prototype.difference` in
    `core-js`](https://github.com/zloirock/core-js#new-set-methods)
-   [`Set.prototype.intersection()`](intersection)
-   [`Set.prototype.isDisjointFrom()`](isdisjointfrom)
-   [`Set.prototype.isSubsetOf()`](issubsetof)
-   [`Set.prototype.isSupersetOf()`](issupersetof)
-   [`Set.prototype.symmetricDifference()`](symmetricdifference)
-   [`Set.prototype.union()`](union)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/difference>

