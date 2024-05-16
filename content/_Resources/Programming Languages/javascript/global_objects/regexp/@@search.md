RegExp.prototype\[@\@search\]()
===============================

 
The `[@@search]()` method of [`RegExp`](../regexp) instances specifies
how [`String.prototype.search`](../string/search) should behave.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
regexp[Symbol.search](str)
```




 
### Parameters

 

[`str`](#str)

:   A [`String`](../string) that is a target of the search.



 
### Return value 

 
The index of the first match between the regular expression and the
given string, or `-1` if no match was found.



 
Description
-----------

 
This method is called internally in
[`String.prototype.search()`](../string/search). For example, the
following two examples return the same result.

 
 
[js]


```js
"abc".search(/a/);

/a/[Symbol.search]("abc");
```


This method does not copy the regular expression, unlike
[`@@split`](@@split) or [`@@matchAll`](@@matchall). However, unlike
[`@@match`](@@match) or [`@@replace`](@@replace), it will set
[`lastIndex`](lastindex) to 0 when execution starts and restore it to
the previous value when it exits, therefore generally avoiding side
effects. This means that the `g` flag has no effect with this method,
and it always returns the first match in the string even when
`lastIndex` is non-zero. This also means sticky regexps will always
search strictly at the beginning of the string.

 
 
[js]


```js
const re = /[abc]/g;
re.lastIndex = 2;
console.log("abc".search(re)); // 0

const re2 = /[bc]/y;
re2.lastIndex = 1;
console.log("abc".search(re2)); // -1
console.log("abc".match(re2)); // [ 'b' ]
```


`@@search` always calls the regex\'s [`exec()`](exec) method exactly
once, and returns the `index` property of the result, or `-1` if the
result is `null`.

This method exists for customizing the search behavior in `RegExp`
subclasses.



 
Examples
--------


 
### Direct call 

 
This method can be used in almost the same way as
[`String.prototype.search()`](../string/search), except for the
different value of `this` and the different arguments order.

 
 
[js]


```js
const re = /-/g;
const str = "2016-01-02";
const result = re[Symbol.search](str);
console.log(result); // 4
```




 
### Using @\@search in subclasses 

 
Subclasses of [`RegExp`](../regexp) can override `[@@search]()` method
to modify the behavior.

 
 
[js]


```js
class MyRegExp extends RegExp {
  constructor(str) {
    super(str);
    this.pattern = str;
  }
  [Symbol.search](str) {
    return str.indexOf(this.pattern);
  }
}

const re = new MyRegExp("a+b");
const str = "ab a+b";
const result = str.search(re); // String.prototype.search calls re[@@search].
console.log(result); // 3
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp.prototype-@\@search]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp.prototype-@@search)

  --------------------------------------------------------------------------------------------------------------------------------


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

`@@search`

50

13

49

37

10

50

49

37

10

5.0

50

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `RegExp.prototype[@@search]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.search()`](../string/search)
-   [`RegExp.prototype[@@match]()`](@@match)
-   [`RegExp.prototype[@@matchAll]()`](@@matchall)
-   [`RegExp.prototype[@@replace]()`](@@replace)
-   [`RegExp.prototype[@@split]()`](@@split)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.test()`](test)
-   [`Symbol.search`](../symbol/search)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@search>

