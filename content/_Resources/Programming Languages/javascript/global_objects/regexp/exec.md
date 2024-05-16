RegExp.prototype.exec()
=======================

 
The `exec()` method of [`RegExp`](../regexp) instances executes a search
with this regular expression for a match in a specified string and
returns a result array, or [`null`](../../operators/null).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
exec(str)
```




 
### Parameters

 

[`str`](#str)

:   The string against which to match the regular expression. All values
    are [coerced to strings](../string#string_coercion), so omitting it
    or passing `undefined` causes `exec()` to search for the string
    `"undefined"`, which is rarely what you want.



 
### Return value 

 
If the match fails, the `exec()` method returns
[`null`](../../operators/null), and sets the regex\'s
[`lastIndex`](lastindex) to `0`.

If the match succeeds, the `exec()` method returns an array and updates
the [`lastIndex`](lastindex) property of the regular expression object.
The returned array has the matched text as the first item, and then one
item for each capturing group of the matched text. The array also has
the following additional properties:

[`index`](#index)

:   The 0-based index of the match in the string.

[`input`](#input)

:   The original string that was matched against.

[`groups`](#groups)

:   A [`null`-prototype object](../object#null-prototype_objects) of
    named capturing groups, whose keys are the names, and values are the
    capturing groups, or [`undefined`](../undefined) if no named
    capturing groups were defined. See [capturing
    groups](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences)
    for more information.

[`indices`](#indices) [Optional]

:   This property is only present when the [`d`](hasindices) flag is
    set. It is an array where each entry represents the bounds of a
    substring match. The index of each element in this array corresponds
    to the index of the respective substring match in the array returned
    by `exec()`. In other words, the first `indices` entry represents
    the entire match, the second `indices` entry represents the first
    capturing group, etc. Each entry itself is a two-element array,
    where the first number represents the match\'s start index, and the
    second number, its end index.

    The `indices` array additionally has a `groups` property, which
    holds a [`null`-prototype object](../object#null-prototype_objects)
    of all named capturing groups. The keys are the names of the
    capturing groups, and each value is a two-element array, with the
    first number being the start index, and the second number being the
    end index of the capturing group. If the regular expression doesn\'t
    contain any named capturing groups, `groups` is `undefined`.



 
Description
-----------

 
JavaScript [`RegExp`](../regexp) objects are *stateful* when they have
the [global](global) or [sticky](sticky) flags set (e.g. `/foo/g` or
`/foo/y`). They store a [`lastIndex`](lastindex) from the previous
match. Using this internally, `exec()` can be used to iterate over
multiple matches in a string of text (with capture groups), as opposed
to getting just the matching strings with
[`String.prototype.match()`](../string/match).

When using `exec()`, the global flag has no effect when the sticky flag
is set --- the match is always sticky.

`exec()` is the primitive method of regexps. Many other regexp methods
call `exec()` internally --- including those called by string methods,
like [`@@replace`](@@replace). While `exec()` itself is powerful (and is
the most efficient), it often does not convey the intent most clearly.

-   If you only care whether the regex matches a string, but not what is
    actually being matched, use [`RegExp.prototype.test()`](test)
    instead.
-   If you are finding all occurrences of a global regex and you don\'t
    care about information like capturing groups, use
    [`String.prototype.match()`](../string/match) instead. In addition,
    [`String.prototype.matchAll()`](../string/matchall) helps to
    simplify matching multiple parts of a string (with capture groups)
    by allowing you to iterate over the matches.
-   If you are executing a match to find its index position in the
    string, use the [`String.prototype.search()`](../string/search)
    method instead.



 
Examples
--------


 
### Using exec() 

 
Consider the following example:

 
 
[js]


```js
// Match "quick brown" followed by "jumps", ignoring characters in between
// Remember "brown" and "jumps"
// Ignore case
const re = /quick\s(?<color>brown).+?(jumps)/dgi;
const result = re.exec("The Quick Brown Fox Jumps Over The Lazy Dog");
```


The following table shows the state of `result` after running this
script:

 
  -------------------------------------------------------------------------------------
  Property                            Value
  ----------------------------------- -------------------------------------------------
  `[0]`                               `"Quick Brown Fox Jumps"`

  `[1]`                               `"Brown"`

  `[2]`                               `"Jumps"`

  `index`                             `4`

  `indices`                           `[[4, 25], [10, 15], [20, 25]]`\
                                      `groups: { color: [10, 15 ]}`

  `input`                             `"The Quick Brown Fox Jumps Over The Lazy Dog"`

  `groups`                            `{ color: "brown" }`
  -------------------------------------------------------------------------------------


In addition, `re.lastIndex` will be set to `25`, due to this regex being
global.



 
### Finding successive matches 

 
If your regular expression uses the
[`g`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags)
flag, you can use the `exec()` method multiple times to find successive
matches in the same string. When you do so, the search starts at the
substring of `str` specified by the regular expression\'s
[`lastIndex`](lastindex) property ([`test()`](test) will also advance
the [`lastIndex`](lastindex) property). Note that the
[`lastIndex`](lastindex) property will not be reset when searching a
different string, it will start its search at its existing
[`lastIndex`](lastindex).

For example, assume you have this script:

 
 
[js]


```js
const myRe = /ab*/g;
const str = "abbcdefabh";
let myArray;
while ((myArray = myRe.exec(str)) !== null) {
  let msg = `Found ${myArray[0]}. `;
  msg += `Next match starts at ${myRe.lastIndex}`;
  console.log(msg);
}
```


This script displays the following text:

```text
Found abb. Next match starts at 3
Found ab. Next match starts at 9
```

 
**Warning:** There are many pitfalls that can lead to this becoming an
infinite loop!

-   Do *not* place the regular expression literal (or
    [`RegExp`](../regexp) constructor) within the `while` condition ---
    it will recreate the regex for every iteration and reset
    [`lastIndex`](lastindex).
-   Be sure that the [global (`g`)
    flag](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags)
    is set, or `lastIndex` will never be advanced.
-   If the regex may match zero-length characters (e.g. `/^/gm`),
    increase its [`lastIndex`](lastindex) manually each time to avoid
    being stuck in the same place.


You can usually replace this kind of code with
[`String.prototype.matchAll()`](../string/matchall) to make it less
error-prone.



 
### Using exec() with RegExp literals 

 
You can also use `exec()` without creating a [`RegExp`](../regexp)
object explicitly:

 
 
[js]


```js
const matches = /(hello \S+)/.exec("This is a hello world!");
console.log(matches[1]);
```


This will log a message containing `'hello world!'`.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp.prototype.exec]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp.prototype.exec)

  -----------------------------------------------------------------------------------------------------------------------


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

`exec`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    guide
-   [`RegExp`](../regexp)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec>

