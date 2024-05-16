RegExp.prototype\[@\@matchAll\]()
=================================

 
The `[@@matchAll]()` method of [`RegExp`](../regexp) instances specifies
how [`String.prototype.matchAll`](../string/matchall) should behave.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
regexp[Symbol.matchAll](str)
```




 
### Parameters

 

[`str`](#str)

:   A [`String`](../string) that is a target of the match.



 
### Return value 

 
An [iterable iterator object](../iterator) (which is not restartable) of
matches. Each match is an array with the same shape as the return value
of [`RegExp.prototype.exec()`](exec).



 
Description
-----------

 
This method is called internally in
[`String.prototype.matchAll()`](../string/matchall). For example, the
following two examples return the same result.

 
 
[js]


```js
"abc".matchAll(/a/g);

/a/g[Symbol.matchAll]("abc");
```


Like [`@@split`](@@split), `@@matchAll` starts by using
[`@@species`](@@species) to construct a new regex, thus avoiding
mutating the original regexp in any way. [`lastIndex`](lastindex) starts
as the original regex\'s value.

 
 
[js]


```js
const regexp = /[a-c]/g;
regexp.lastIndex = 1;
const str = "abc";
Array.from(str.matchAll(regexp), (m) => `${regexp.lastIndex}${m[0]}`);
// [ "1 b", "1 c" ]
```


The validation that the input is a global regex happens in
[`String.prototype.matchAll()`](../string/matchall). `@@matchAll` does
not validate the input. If the regex is not global, the returned
iterator yields the [`exec()`](exec) result once and then returns
`undefined`. If the regexp is global, each time the returned iterator\'s
`next()` method is called, the regex\'s [`exec()`](exec) is called and
the result is yielded.

When the regex is sticky and global, it will still perform sticky
matches --- i.e. it will not match any occurrences beyond the
`lastIndex`.

 
 
[js]


```js
console.log(Array.from("ab-c".matchAll(/[abc]/gy)));
// [ [ "a" ], [ "b" ] ]
```


If the current match is an empty string, the [`lastIndex`](lastindex)
will still be advanced. If the regex has the [`u`](unicode) flag, it
advances by one Unicode code point; otherwise, it advances by one UTF-16
code point.

 
 
[js]


```js
console.log(Array.from("😄".matchAll(/(?:)/g)));
// [ [ "" ], [ "" ], [ "" ] ]

console.log(Array.from("😄".matchAll(/(?:)/gu)));
// [ [ "" ], [ "" ] ]
```


This method exists for customizing the behavior of `matchAll()` in
[`RegExp`](../regexp) subclasses.



 
Examples
--------


 
### Direct call 

 
This method can be used in almost the same way as
[`String.prototype.matchAll()`](../string/matchall), except for the
different value of `this` and the different order of arguments.

 
 
[js]


```js
const re = /[0-9]+/g;
const str = "2016-01-02";
const result = re[Symbol.matchAll](str);

console.log(Array.from(result, (x) => x[0]));
// [ "2016", "01", "02" ]
```




 
### Using @\@matchAll in subclasses 

 
Subclasses of [`RegExp`](../regexp) can override the `[@@matchAll]()`
method to modify the default behavior.

For example, to return an [`Array`](../array) instead of an
[iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators):

 
 
[js]


```js
class MyRegExp extends RegExp {
  [Symbol.matchAll](str) {
    const result = RegExp.prototype[Symbol.matchAll].call(this, str);
    return result ? Array.from(result) : null;
  }
}

const re = new MyRegExp("([0-9]+)-([0-9]+)-([0-9]+)", "g");
const str = "2016-01-02|2019-03-07";
const result = str.matchAll(re);

console.log(result[0]);
// [ "2016-01-02", "2016", "01", "02" ]

console.log(result[1]);
// [ "2019-03-07", "2019", "03", "07" ]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp-prototype-matchall]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp-prototype-matchall)

  -------------------------------------------------------------------------------------------------------------------------------


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

`@@matchAll`

73

79

67

60

13

73

67

52

13

5.0

73

1.0

12.0.0

 
See also 
--------

 
-   [Polyfill of `RegExp.prototype[@@matchAll]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.matchAll()`](../string/matchall)
-   [`RegExp.prototype[@@match]()`](@@match)
-   [`RegExp.prototype[@@replace]()`](@@replace)
-   [`RegExp.prototype[@@search]()`](@@search)
-   [`RegExp.prototype[@@split]()`](@@split)
-   [`Symbol.matchAll`](../symbol/matchall)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@matchAll>

