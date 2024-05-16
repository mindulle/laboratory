String.prototype\[@\@iterator\]()
=================================

 
The `[@@iterator]()` method of [`String`](../string) values implements
the [iterable protocol](../../iteration_protocols) and allows strings to
be consumed by most syntaxes expecting iterables, such as the [spread
syntax](../../operators/spread_syntax) and
[`for...of`](../../statements/for...of) loops. It returns a [string
iterator object](../iterator) that yields the Unicode code points of the
string value as individual strings.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
string[Symbol.iterator]()
```




 
### Parameters

 
None.



 
### Return value 

 
A new [iterable iterator object](../iterator) that yields the Unicode
code points of the string value as individual strings.



 
Description
-----------

 
Strings are iterated by Unicode code points. This means grapheme
clusters will be split, but surrogate pairs will be preserved.

 
 
[js]


```js
// "Backhand Index Pointing Right: Dark Skin Tone"
[..."👉🏿"]; // ['👉', '🏿']
// splits into the basic "Backhand Index Pointing Right" emoji and
// the "Dark skin tone" emoji

// "Family: Man, Boy"
[..."👨‍👦"]; // [ '👨', '‍', '👦' ]
// splits into the "Man" and "Boy" emoji, joined by a ZWJ
```




 
Examples
--------


 
### Iteration using for\...of loop 

 
Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes strings
[iterable](../../iteration_protocols#the_iterable_protocol), and
iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.

 
 
[js]


```js
const str = "A\uD835\uDC68B\uD835\uDC69C\uD835\uDC6A";

for (const v of str) {
  console.log(v);
}
// "A"
// "\uD835\uDC68"
// "B"
// "\uD835\uDC69"
// "C"
// "\uD835\uDC6A"
```




 
### Manually hand-rolling the iterator 

 
You may still manually call the `next()` method of the returned iterator
object to achieve maximum control over the iteration process.

 
 
[js]


```js
const str = "A\uD835\uDC68";

const strIter = str[Symbol.iterator]();

console.log(strIter.next().value); // "A"
console.log(strIter.next().value); // "\uD835\uDC68"
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype-@\@iterator]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype-@@iterator)

  ------------------------------------------------------------------------------------------------------------------------------------


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

`@@iterator`

38

12

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

9

38

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

9

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `String.prototype[@@iterator]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [Text
    formatting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Text_formatting)
    guide
-   [`Symbol.iterator`](../symbol/iterator)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/@@iterator>

