Set.prototype.isDisjointFrom()
==============================

[Limited availability]
---------------------------------

 
This feature is not Baseline because it does not work in some of the
most widely-used browsers.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FSet%2FisDisjointFrom&level=not)


 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `isDisjointFrom()` method of [`Set`](../set) instances takes a set
and returns a boolean indicating if this set has no elements in common
with the given set.


 
Syntax
------

 
 
 
[js]


```js
isDisjointFrom(other)
```




 
### Parameters

 

[`other`](#other)

:   A [`Set`](../set) object, or [set-like](../set#set-like_objects)
    object.



 
### Return value 

 
`true` if this set has no elements in common with the `other` set, and
`false` otherwise.



 
Description
-----------

 
Two sets are *disjoint* if they have no elements in common. In
mathematical notation:

$$A\text{is\ disjoint\ from}B\Leftrightarrow A \cap B = \varnothing$$

And using Venn diagram:




`isDisjointFrom()` accepts [set-like](../set#set-like_objects) objects
as the `other` parameter. It requires [`this`](../../operators/this) to
be an actual [`Set`](../set) instance, because it directly retrieves the
underlying data stored in `this` without invoking any user code. Then,
its behavior depends on the sizes of `this` and `other`:

-   If there are more elements in `this` than `other.size`, then it
    iterates over `other` by calling its `keys()` method, and if any
    element in `other` is present in `this`, it returns `false` (and
    closes the `keys()` iterator by calling its `return()` method).
    Otherwise, it returns `true`.
-   Otherwise, it iterates over the elements in `this`, and returns
    `false` if any element `e` in `this` causes `other.has(e)` to return
    a [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value. Otherwise, it returns `true`.

Because of this implementation, the efficiency of `isDisjointFrom()`
mostly depends on the size of the smaller set between `this` and `other`
(assuming sets can be accessed in sublinear time).



 
Examples
--------


 
### Using isDisjointFrom() 

 
The set of perfect squares (\<20) is disjoint from the set of prime
numbers (\<20), because a perfect square is by definition decomposable
into the product of two integers, while 1 is also not considered a prime
number:

 
 
[js]


```js
const primes = new Set([2, 3, 5, 7, 11, 13, 17, 19]);
const squares = new Set([1, 4, 9, 16]);
console.log(primes.isDisjointFrom(squares)); // true
```


The set of perfect squares (\<20) is not disjoint from the set of
composite numbers (\<20), because all non-1 perfect squares are by
definition composite numbers:

 
 
[js]


```js
const composites = new Set([4, 6, 8, 9, 10, 12, 14, 15, 16, 18]);
const squares = new Set([1, 4, 9, 16]);
console.log(composites.isDisjointFrom(squares)); // false
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------
  [Set methods\
  [\#
  sec-set.prototype.isDisjointFrom]](https://tc39.es/proposal-set-methods/#sec-set.prototype.isDisjointFrom)

  --------------------------------------------------------------------------------------------------------------------


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

`isDisjointFrom`

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

 
-   [Polyfill of `Set.prototype.isDisjointFrom` in
    `core-js`](https://github.com/zloirock/core-js#new-set-methods)
-   [`Set.prototype.difference()`](difference)
-   [`Set.prototype.intersection()`](intersection)
-   [`Set.prototype.isSubsetOf()`](issubsetof)
-   [`Set.prototype.isSupersetOf()`](issupersetof)
-   [`Set.prototype.symmetricDifference()`](symmetricdifference)
-   [`Set.prototype.union()`](union)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/isDisjointFrom>

