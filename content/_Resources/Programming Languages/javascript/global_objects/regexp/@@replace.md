RegExp.prototype\[@\@replace\]()
================================

 
The `[@@replace]()` method of [`RegExp`](../regexp) instances specifies
how [`String.prototype.replace()`](../string/replace) and
[`String.prototype.replaceAll()`](../string/replaceall) should behave
when the regular expression is passed in as the pattern.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
regexp[Symbol.replace](str, replacement)
```




 
### Parameters

 

[`str`](#str)

:   A [`String`](../string) that is a target of the replacement.

[`replacement`](#replacement)

:   Can be a string or a function.

    -   If it\'s a string, it will replace the substring matched by the
        current regexp. A number of special replacement patterns are
        supported; see the [Specifying a string as the
        replacement](../string/replace#specifying_a_string_as_the_replacement)
        section of `String.prototype.replace`.
    -   If it\'s a function, it will be invoked for every match and the
        return value is used as the replacement text. The arguments
        supplied to this function are described in the [Specifying a
        function as the
        replacement](../string/replace#specifying_a_function_as_the_replacement)
        section of `String.prototype.replace`.



 
### Return value 

 
A new string, with one, some, or all matches of the pattern replaced by
the specified replacement.



 
Description
-----------

 
This method is called internally in
[`String.prototype.replace()`](../string/replace) and
[`String.prototype.replaceAll()`](../string/replaceall) if the `pattern`
argument is a [`RegExp`](../regexp) object. For example, the following
two examples return the same result.

 
 
[js]


```js
"abc".replace(/a/, "A");

/a/[Symbol.replace]("abc", "A");
```


If the regex is global (with the `g` flag), the regex\'s
[`exec()`](exec) method will be repeatedly called until `exec()` returns
`null`. Otherwise, `exec()` would only be called once. For each `exec()`
result, the substitution will be prepared based on the description in
[`String.prototype.replace()`](../string/replace#description).

Because `@@replace` would keep calling `exec()` until it returns `null`,
and `exec()` would automatically reset the regex\'s
[`lastIndex`](lastindex) to 0 when the last match fails, `@@replace`
would typically not have side effects when it exits. However, when the
regex is [sticky](sticky) but not global, `lastIndex` would not be
reset. In this case, each call to `replace()` may return a different
result.

 
 
[js]


```js
const re = /a/y;

for (let i = 0; i < 5; i++) {
  console.log("aaa".replace(re, "b"), re.lastIndex);
}

// baa 1
// aba 2
// aab 3
// aaa 0
// baa 1
```


When the regex is sticky and global, it would still perform sticky
matches --- i.e. it would fail to match any occurrences beyond the
`lastIndex`.

 
 
[js]


```js
console.log("aa-a".replace(/a/gy, "b")); // "bb-a"
```


If the current match is an empty string, the `lastIndex` would still be
advanced --- if the regex is
[Unicode-aware](unicode#unicode-aware_mode), it would advance by one
Unicode code point; otherwise, it advances by one UTF-16 code unit.

 
 
[js]


```js
console.log("😄".replace(/(?:)/g, " ")); // " \ud83d \ude04 "
console.log("😄".replace(/(?:)/gu, " ")); // " 😄 "
```


This method exists for customizing replace behavior in `RegExp`
subclasses.



 
Examples
--------


 
### Direct call 

 
This method can be used in almost the same way as
[`String.prototype.replace()`](../string/replace), except the different
`this` and the different arguments order.

 
 
[js]


```js
const re = /-/g;
const str = "2016-01-01";
const newstr = re[Symbol.replace](str, ".");
console.log(newstr); // 2016.01.01
```




 
### Using @\@replace in subclasses 

 
Subclasses of [`RegExp`](../regexp) can override the `[@@replace]()`
method to modify the default behavior.

 
 
[js]


```js
class MyRegExp extends RegExp {
  constructor(pattern, flags, count) {
    super(pattern, flags);
    this.count = count;
  }
  [Symbol.replace](str, replacement) {
    // Perform @@replace |count| times.
    let result = str;
    for (let i = 0; i < this.count; i++) {
      result = RegExp.prototype[Symbol.replace].call(this, result, replacement);
    }
    return result;
  }
}

const re = new MyRegExp("\\d", "", 3);
const str = "01234567";
const newstr = str.replace(re, "#"); // String.prototype.replace calls re[@@replace].
console.log(newstr); // ###34567
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp.prototype-@\@replace]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp.prototype-@@replace)

  ----------------------------------------------------------------------------------------------------------------------------------


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

`@@replace`

50

79

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

 
-   [Polyfill of `RegExp.prototype[@@replace]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.replace()`](../string/replace)
-   [`String.prototype.replaceAll()`](../string/replaceall)
-   [`RegExp.prototype[@@match]()`](@@match)
-   [`RegExp.prototype[@@matchAll]()`](@@matchall)
-   [`RegExp.prototype[@@search]()`](@@search)
-   [`RegExp.prototype[@@split]()`](@@split)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.test()`](test)
-   [`Symbol.replace`](../symbol/replace)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@replace>

