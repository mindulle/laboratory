RegExp.prototype\[@\@match\]()
==============================

 
The `[@@match]()` method of [`RegExp`](../regexp) instances specifies
how [`String.prototype.match()`](../string/match) should behave. In
addition, its presence (or absence) can influence whether an object is
regarded as a regular expression.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
regexp[Symbol.match](str)
```




 
### Parameters

 

[`str`](#str)

:   A [`String`](../string) that is a target of the match.



 
### Return value 

 
An [`Array`](../array) whose contents depend on the presence or absence
of the global (`g`) flag, or [`null`](../../operators/null) if no
matches are found.

-   If the `g` flag is used, all results matching the complete regular
    expression will be returned, but capturing groups are not included.
-   If the `g` flag is not used, only the first complete match and its
    related capturing groups are returned. In this case, `match()` will
    return the same result as [`RegExp.prototype.exec()`](exec) (an
    array with some extra properties).



 
Description
-----------

 
This method is called internally in
[`String.prototype.match()`](../string/match).

For example, the following two examples return same result.

 
 
[js]


```js
"abc".match(/a/);

/a/[Symbol.match]("abc");
```


If the regex is global (with the `g` flag), the regex\'s
[`exec()`](exec) method will be repeatedly called until `exec()` returns
`null`. Otherwise, `exec()` would only be called once and its result
becomes the return value of `@@match`.

Because `@@match` would keep calling `exec()` until it returns `null`,
and `exec()` would automatically reset the regex\'s
[`lastIndex`](lastindex) to 0 when the last match fails, `@@match` would
typically not have side effects when it exits. However, when the regex
is [sticky](sticky) but not global, `lastIndex` would not be reset. In
this case, each call to `match()` may return a different result.

 
 
[js]


```js
const re = /[abc]/y;
for (let i = 0; i < 5; i++) {
  console.log("abc".match(re), re.lastIndex);
}
// [ 'a' ] 1
// [ 'b' ] 2
// [ 'c' ] 3
// null 0
// [ 'a' ] 1
```


When the regex is sticky and global, it would still perform sticky
matches --- i.e. it would fail to match any occurrences beyond the
`lastIndex`.

 
 
[js]


```js
console.log("ab-c".match(/[abc]/gy)); // [ 'a', 'b' ]
```


If the current match is an empty string, the `lastIndex` would still be
advanced --- if the regex is
[Unicode-aware](unicode#unicode-aware_mode), it would advance by one
Unicode code point; otherwise, it advances by one UTF-16 code unit.

 
 
[js]


```js
console.log("😄".match(/(?:)/g)); // [ '', '', '' ]
console.log("😄".match(/(?:)/gu)); // [ '', '' ]
```


This method exists for customizing match behavior within `RegExp`
subclasses.

In addition, the `@@match` property is used to check [whether an object
is a regular expression](../regexp#special_handling_for_regexes).



 
Examples
--------


 
### Direct call 

 
This method can be used in *almost* the same way as
[`String.prototype.match()`](../string/match), except the different
`this` and the different arguments order.

 
 
[js]


```js
const re = /[0-9]+/g;
const str = "2016-01-02";
const result = re[Symbol.match](str);
console.log(result); // ["2016", "01", "02"]
```




 
### Using @\@match in subclasses 

 
Subclasses of [`RegExp`](../regexp) can override the `[@@match]()`
method to modify the default behavior.

 
 
[js]


```js
class MyRegExp extends RegExp {
  [Symbol.match](str) {
    const result = RegExp.prototype[Symbol.match].call(this, str);
    if (!result) return null;
    return {
      group(n) {
        return result[n];
      },
    };
  }
}

const re = new MyRegExp("([0-9]+)-([0-9]+)-([0-9]+)");
const str = "2016-01-02";
const result = str.match(re); // String.prototype.match calls re[@@match].
console.log(result.group(1)); // 2016
console.log(result.group(2)); // 01
console.log(result.group(3)); // 02
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp.prototype-@\@match]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp.prototype-@@match)

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

`@@match`

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

 
-   [Polyfill of `RegExp.prototype[@@match]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.match()`](../string/match)
-   [`RegExp.prototype[@@matchAll]()`](@@matchall)
-   [`RegExp.prototype[@@replace]()`](@@replace)
-   [`RegExp.prototype[@@search]()`](@@search)
-   [`RegExp.prototype[@@split]()`](@@split)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.test()`](test)
-   [`Symbol.match`](../symbol/match)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@match>

