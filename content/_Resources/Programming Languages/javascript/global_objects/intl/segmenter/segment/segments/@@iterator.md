Segments.prototype\[@\@iterator\]()
===================================

 
The `[@@iterator]()` method of [`Segments`](../segments) instances
implements the [iterable protocol](../../../../../iteration_protocols)
and allows `Segments` objects to be consumed by most syntaxes expecting
iterables, such as the [spread
syntax](../../../../../operators/spread_syntax) and
[`for...of`](../../../../../statements/for...of) loops. It returns a
[segments iterator object](../../../../iterator) that yields data about
each segment.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
segments[Symbol.iterator]()
```




 
### Parameters

 
None.



 
### Return value 

 
A new [iterable iterator object](../../../../iterator) that yields data
about each segment. Each yielded object has the same properties as the
object returned by the [`containing()`](containing) method.



 
Examples
--------


 
### Iteration using for\...of loop 

 
Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes `Segments` objects
[iterable](../../../../../iteration_protocols#the_iterable_protocol),
and iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.

 
 
[js]


```js
const segmenter = new Intl.Segmenter("zh-CN", { granularity: "word" });
const input = "你好，世界！我爱编程。";

for (const value of segmenter.segment(input)) {
  console.log(value);
}

/*
{segment: '你好', index: 0, input: '你好，世界！我爱编程。', isWordLike: true}
{segment: '，', index: 2, input: '你好，世界！我爱编程。', isWordLike: false}
{segment: '世界', index: 3, input: '你好，世界！我爱编程。', isWordLike: true}
{segment: '！', index: 5, input: '你好，世界！我爱编程。', isWordLike: false}
{segment: '我', index: 6, input: '你好，世界！我爱编程。', isWordLike: true}
{segment: '爱', index: 7, input: '你好，世界！我爱编程。', isWordLike: true}
{segment: '编', index: 8, input: '你好，世界！我爱编程。', isWordLike: true}
{segment: '程', index: 9, input: '你好，世界！我爱编程。', isWordLike: true}
{segment: '。', index: 10, input: '你好，世界！我爱编程。', isWordLike: false}
*/
```




 
### Manually hand-rolling the iterator 

 
You may still manually call the `next()` method of the returned iterator
object to achieve maximum control over the iteration process.

 
 
[js]


```js
const segmenter = new Intl.Segmenter("fr", { granularity: "word" });
const input = "Moi ? N'est-ce pas ?";
const segments = segmenter.segment(input);
const iterator = segments[Symbol.iterator]();

let result = iterator.next();

while (!result.done) {
  console.log(result.value);
  result = iterator.next();
}

/*
{segment: 'Moi', index: 0, input: "Moi ? N'est-ce pas ?", isWordLike: true}
{segment: ' ', index: 3, input: "Moi ? N'est-ce pas ?", isWordLike: false}
{segment: '?', index: 4, input: "Moi ? N'est-ce pas ?", isWordLike: false}
{segment: ' ', index: 5, input: "Moi ? N'est-ce pas ?", isWordLike: false}
{segment: "N'est", index: 6, input: "Moi ? N'est-ce pas ?", isWordLike: true}
{segment: '-', index: 11, input: "Moi ? N'est-ce pas ?", isWordLike: false}
{segment: 'ce', index: 12, input: "Moi ? N'est-ce pas ?", isWordLike: true}
{segment: ' ', index: 14, input: "Moi ? N'est-ce pas ?", isWordLike: false}
{segment: 'pas', index: 15, input: "Moi ? N'est-ce pas ?", isWordLike: true}
{segment: ' ', index: 18, input: "Moi ? N'est-ce pas ?", isWordLike: false}
{segment: '?', index: 19, input: "Moi ? N'est-ce pas ?", isWordLike: false}
*/
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\# sec-%segmentsprototype%-@\@iterator]](#)

  -----------------------------------------------------------------------


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

87

87

No

73

14.1

87

No

62

14.5

14.0

87

1.8

16.0.0

 
See also 
--------

 
-   [`Intl.Segmenter`](../../../segmenter)
-   [`Intl.Segmenter.prototype.segment()`](../../segment)
-   [`Symbol.iterator`](../../../../symbol/iterator)
-   [Iteration protocols](../../../../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/segment/Segments/@@iterator>

