String.prototype.matchAll()
===========================

 
The `matchAll()` method of [`String`](../string) values returns an
iterator of all results matching this string against a [regular
expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions),
including [capturing
groups](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
matchAll(regexp)
```




 
### Parameters

 

[`regexp`](#regexp)

:   A regular expression object, or any object that has a
    [`Symbol.matchAll`](../symbol/matchall) method.

    If `regexp` is not a `RegExp` object and does not have a
    `Symbol.matchAll` method, it is implicitly converted to a
    [`RegExp`](../regexp) by using `new RegExp(regexp, 'g')`.

    If `regexp` [is a regex](../regexp#special_handling_for_regexes),
    then it must have the global (`g`) flag set, or a
    [`TypeError`](../typeerror) is thrown.



 
### Return value 

 
An [iterable iterator object](../iterator) (which is not restartable) of
matches. Each match is an array with the same shape as the return value
of [`RegExp.prototype.exec()`](../regexp/exec).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if the `regexp` [is a
    regex](../regexp#special_handling_for_regexes) that does not have
    the global (`g`) flag set (its [`flags`](../regexp/flags) property
    does not contain `"g"`).



 
Description
-----------

 
The implementation of `String.prototype.matchAll` itself is very simple
--- it simply calls the `Symbol.matchAll` method of the argument with
the string as the first parameter (apart from the extra input validation
that the regex is global). The actual implementation comes from
[`RegExp.prototype[@@matchAll]()`](../regexp/@@matchall).



 
Examples
--------


 
### Regexp.prototype.exec() and matchAll() 

 
Without `matchAll()`, it\'s possible to use calls to
[`regexp.exec()`](../regexp/exec) (and regexes with the `g` flag) in a
loop to obtain all the matches:

 
 
[js]


```js
const regexp = /foo[a-z]*/g;
const str = "table football, foosball";
let match;

while ((match = regexp.exec(str)) !== null) {
  console.log(
    `Found ${match[0]} start=${match.index} end=${regexp.lastIndex}.`,
  );
}
// Found football start=6 end=14.
// Found foosball start=16 end=24.
```


With `matchAll()` available, you can avoid the
[`while`](../../statements/while) loop and `exec` with `g`. Instead, you
get an iterator to use with the more convenient
[`for...of`](../../statements/for...of), [array
spreading](../../operators/spread_syntax), or
[`Array.from()`](../array/from) constructs:

 
 
[js]


```js
const regexp = /foo[a-z]*/g;
const str = "table football, foosball";
const matches = str.matchAll(regexp);

for (const match of matches) {
  console.log(
    `Found ${match[0]} start=${match.index} end=${
      match.index + match[0].length
    }.`,
  );
}
// Found football start=6 end=14.
// Found foosball start=16 end=24.

// matches iterator is exhausted after the for...of iteration
// Call matchAll again to create a new iterator
Array.from(str.matchAll(regexp), (m) => m[0]);
// [ "football", "foosball" ]
```


`matchAll` will throw an exception if the `g` flag is missing.

 
 
[js]


```js
const regexp = /[a-c]/;
const str = "abc";
str.matchAll(regexp);
// TypeError
```


`matchAll` internally makes a clone of the `regexp` --- so, unlike
[`regexp.exec()`](../regexp/exec), `lastIndex` does not change as the
string is scanned.

 
 
[js]


```js
const regexp = /[a-c]/g;
regexp.lastIndex = 1;
const str = "abc";
Array.from(str.matchAll(regexp), (m) => `${regexp.lastIndex}${m[0]}`);
// [ "1 b", "1 c" ]
```


However, this means that unlike using [`regexp.exec()`](../regexp/exec)
in a loop, you can\'t mutate `lastIndex` to make the regex advance or
rewind.



 
### Better access to capturing groups (than String.prototype.match()) 

 
Another compelling reason for `matchAll` is the improved access to
capture groups.

Capture groups are ignored when using [`match()`](match) with the global
`g` flag:

 
 
[js]


```js
const regexp = /t(e)(st(\d?))/g;
const str = "test1test2";

str.match(regexp); // ['test1', 'test2']
```


Using `matchAll`, you can access capture groups easily:

 
 
[js]


```js
const array = [...str.matchAll(regexp)];

array[0];
// ['test1', 'e', 'st1', '1', index: 0, input: 'test1test2', length: 4]
array[1];
// ['test2', 'e', 'st2', '2', index: 5, input: 'test1test2', length: 4]
```




 
### Using matchAll() with a non-RegExp implementing @\@matchAll 

 
If an object has a `Symbol.matchAll` method, it can be used as a custom
matcher. The return value of `Symbol.matchAll` becomes the return value
of `matchAll()`.

 
 
[js]


```js
const str = "Hmm, this is interesting.";

str.matchAll({
  [Symbol.matchAll](str) {
    return [["Yes, it's interesting."]];
  },
}); // returns [["Yes, it's interesting."]]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.matchall]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.matchall)

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

`matchAll`

73

79

67

60

13

73

67

52

13

11.0

73

1.0

12.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.matchAll` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.match()`](match)
-   [Regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    guide
-   [Groups and
    backreferences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences)
    guide
-   [`RegExp`](../regexp)
-   [`RegExp.prototype.exec()`](../regexp/exec)
-   [`RegExp.prototype.test()`](../regexp/test)
-   [`RegExp.prototype[@@matchAll]()`](../regexp/@@matchall)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/matchAll>

