RegExp
======

 
The `RegExp` object is used for matching text with a pattern.

For an introduction to regular expressions, read the [Regular
expressions
chapter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
in the JavaScript guide. For detailed information of regular expression
syntax, read the [regular expression reference](../regular_expressions).


 
Description
-----------


 
### Literal notation and constructor 

 
There are two ways to create a `RegExp` object: a *literal notation* and
a *constructor*.

-   The *literal notation* takes a pattern between two slashes, followed
    by optional
    [flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags),
    after the second slash.
-   The *constructor function* takes either a string or a `RegExp`
    object as its first parameter and a string of optional
    [flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags)
    as its second parameter.

The following three expressions create the same regular expression
object:

 
 
[js]


```js
const re = /ab+c/i; // literal notation
// OR
const re = new RegExp("ab+c", "i"); // constructor with string pattern as first argument
// OR
const re = new RegExp(/ab+c/, "i"); // constructor with regular expression literal as first argument
```


Before regular expressions can be used, they have to be compiled. This
process allows them to perform matches more efficiently. More about the
process can be found in [dotnet
docs](https://docs.microsoft.com/dotnet/standard/base-types/compilation-and-reuse-in-regular-expressions).

The literal notation results in compilation of the regular expression
when the expression is evaluated. On the other hand, the constructor of
the `RegExp` object, `new RegExp('ab+c')`, results in runtime
compilation of the regular expression.

Use a string as the first argument to the `RegExp()` constructor when
you want to [build the regular expression from dynamic
input](#building_a_regular_expression_from_dynamic_inputs).



 
### Flags in constructor 

 
The expression `new RegExp(/ab+c/, flags)` will create a new `RegExp`
using the source of the first parameter and the
[flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags)
provided by the second.

When using the constructor function, the normal string escape rules
(preceding special characters with `\` when included in a string) are
necessary.

For example, the following are equivalent:

 
 
[js]


```js
const re = /\w+/;
// OR
const re = new RegExp("\\w+");
```




 
### Special handling for regexes 

 
 
**Note:** Whether something is a \"regex\" can be
[duck-typed](https://en.wikipedia.org/wiki/Duck_typing). It doesn\'t
have to be a `RegExp`!


Some built-in methods would treat regexes specially. They decide whether
`x` is a regex through [multiple
steps](https://tc39.es/ecma262/multipage/abstract-operations.html#sec-isregexp):

1.  `x` must be an object (not a primitive).
2.  If [`x[Symbol.match]`](symbol/match) is not `undefined`, check if
    it\'s
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).
3.  Otherwise, if `x[Symbol.match]` is `undefined`, check if `x` had
    been created with the `RegExp` constructor. (This step should rarely
    happen, since if `x` is a `RegExp` object that have not been
    tampered with, it should have a `Symbol.match` property.)

Note that in most cases, it would go through the `Symbol.match` check,
which means:

-   An actual `RegExp` object whose `Symbol.match` property\'s value is
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) but
    not `undefined` (even with everything else intact, like
    [`exec`](regexp/exec) and [`@@replace`](regexp/@@replace)) can be
    used as if it\'s not a regex.
-   A non-`RegExp` object with a `Symbol.match` property will be treated
    as if it\'s a regex.

This choice was made because `@@match` is the most indicative property
that something is intended to be used for matching. (`exec` could also
be used, but because it\'s not a symbol property, there would be too
many false positives.) The places that treat regexes specially include:

-   [`String.prototype.endsWith()`](string/endswith),
    [`startsWith()`](string/startswith), and
    [`includes()`](string/includes) throw a [`TypeError`](typeerror) if
    the first argument is a regex.
-   [`String.prototype.matchAll()`](string/matchall) and
    [`replaceAll()`](string/replaceall) check whether the
    [global](regexp/global) flag is set if the first argument is a regex
    before invoking its [`@@matchAll`](symbol/matchall) or
    [`@@replace`](symbol/replace) method.
-   The [`RegExp()`](regexp/regexp) constructor directly returns the
    `pattern` argument only if `pattern` is a regex (among a few other
    conditions). If `pattern` is a regex, it would also interrogate
    `pattern`\'s `source` and `flags` properties instead of coercing
    `pattern` to a string.

For example, [`String.prototype.endsWith()`](string/endswith) would
coerce all inputs to strings, but it would throw if the argument is a
regex, because it\'s only designed to match strings, and using a regex
is likely a developer mistake.

 
 
[js]


```js
"foobar".endsWith({ toString: () => "bar" }); // true
"foobar".endsWith(/bar/); // TypeError: First argument to String.prototype.endsWith must not be a regular expression
```


You can get around the check by setting `@@match` to a
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value
that\'s not `undefined`. This would mean that the regex cannot be used
for `String.prototype.match()` (since without `@@match`, `match()` would
construct a new `RegExp` object with the two enclosing slashes added by
[`re.toString()`](regexp/tostring)), but it can be used for virtually
everything else.

 
 
[js]


```js
const re = /bar/g;
re[Symbol.match] = false;
"/bar/g".endsWith(re); // true
re.exec("bar"); // [ 'bar', index: 0, input: 'bar', groups: undefined ]
"bar & bar".replace(re, "foo"); // 'foo & foo'
```




 
### Perl-like RegExp properties 

 
Note that several of the [`RegExp`](regexp) properties have both long
and short (Perl-like) names. Both names always refer to the same value.
(Perl is the programming language from which JavaScript modeled its
regular expressions.) See also [deprecated `RegExp`
properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#regexp).



 
Constructor
-----------

 

[`RegExp()`](regexp/regexp)

:   Creates a new `RegExp` object.



 
Static properties 
-----------------

 

[`RegExp.$1, …, RegExp.$9`](regexp/n) [Deprecated]

:   Static read-only properties that contain parenthesized substring
    matches.

[`RegExp.input ($_)`](regexp/input) [Deprecated]

:   A static property that contains the last string against which a
    regular expression was successfully matched.

[`RegExp.lastMatch ($&)`](regexp/lastmatch) [Deprecated]

:   A static read-only property that contains the last matched
    substring.

[`RegExp.lastParen ($+)`](regexp/lastparen) [Deprecated]

:   A static read-only property that contains the last parenthesized
    substring match.

[`` RegExp.leftContext ($`) ``](regexp/leftcontext) [Deprecated]

:   A static read-only property that contains the substring preceding
    the most recent match.

[`RegExp.rightContext ($')`](regexp/rightcontext) [Deprecated]

:   A static read-only property that contains the substring following
    the most recent match.

[`RegExp[@@species]`](regexp/@@species)

:   The constructor function that is used to create derived objects.



 
Instance properties 
-------------------

 
These properties are defined on `RegExp.prototype` and shared by all
`RegExp` instances.

[`RegExp.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `RegExp` instances, the initial value is the
    [`RegExp`](regexp/regexp) constructor.

[`RegExp.prototype.dotAll`](regexp/dotall)

:   Whether `.` matches newlines or not.

[`RegExp.prototype.flags`](regexp/flags)

:   A string that contains the flags of the `RegExp` object.

[`RegExp.prototype.global`](regexp/global)

:   Whether to test the regular expression against all possible matches
    in a string, or only against the first.

[`RegExp.prototype.hasIndices`](regexp/hasindices)

:   Whether the regular expression result exposes the start and end
    indices of captured substrings.

[`RegExp.prototype.ignoreCase`](regexp/ignorecase)

:   Whether to ignore case while attempting a match in a string.

[`RegExp.prototype.multiline`](regexp/multiline)

:   Whether or not to search in strings across multiple lines.

[`RegExp.prototype.source`](regexp/source)

:   The text of the pattern.

[`RegExp.prototype.sticky`](regexp/sticky)

:   Whether or not the search is sticky.

[`RegExp.prototype.unicode`](regexp/unicode)

:   Whether or not Unicode features are enabled.

[`RegExp.prototype.unicodeSets`](regexp/unicodesets)

:   Whether or not the `v` flag, an upgrade to the `u` mode, is enabled.

These properties are own properties of each `RegExp` instance.

[`lastIndex`](regexp/lastindex)

:   The index at which to start the next match.



 
Instance methods 
----------------

 

[`RegExp.prototype.compile()`](regexp/compile) [Deprecated]

:   (Re-)compiles a regular expression during execution of a script.

[`RegExp.prototype.exec()`](regexp/exec)

:   Executes a search for a match in its string parameter.

[`RegExp.prototype.test()`](regexp/test)

:   Tests for a match in its string parameter.

[`RegExp.prototype.toString()`](regexp/tostring)

:   Returns a string representing the specified object. Overrides the
    [`Object.prototype.toString()`](object/tostring) method.

[`RegExp.prototype[@@match]()`](regexp/@@match)

:   Performs match to given string and returns match result.

[`RegExp.prototype[@@matchAll]()`](regexp/@@matchall)

:   Returns all matches of the regular expression against a string.

[`RegExp.prototype[@@replace]()`](regexp/@@replace)

:   Replaces matches in given string with new substring.

[`RegExp.prototype[@@search]()`](regexp/@@search)

:   Searches the match in given string and returns the index the pattern
    found in the string.

[`RegExp.prototype[@@split]()`](regexp/@@split)

:   Splits given string into an array by separating the string into
    substrings.



 
Examples
--------


 
### Using a regular expression to change data format 

 
The following script uses the
[`String.prototype.replace()`](string/replace) method to match a name in
the format *first last* and output it in the format *last, first*.

In the replacement text, the script uses `$1` and `$2` to indicate the
results of the corresponding matching parentheses in the regular
expression pattern.

 
 
[js]


```js
const re = /(\w+)\s(\w+)/;
const str = "Maria Cruz";
const newstr = str.replace(re, "$2, $1");
console.log(newstr);
```


This displays `"Cruz, Maria"`.



 
### Using regular expression to split lines with different line endings/ends of line/line breaks 

 
The default line ending varies depending on the platform (Unix, Windows,
etc.). The line splitting provided in this example works on all
platforms.

 
 
[js]


```js
const text = "Some text\nAnd some more\r\nAnd yet\rThis is the end";
const lines = text.split(/\r\n|\r|\n/);
console.log(lines); // [ 'Some text', 'And some more', 'And yet', 'This is the end' ]
```


Note that the order of the patterns in the regular expression matters.



 
### Using regular expression on multiple lines 

 
 
 
[js]


```js
const s = "Please yes\nmake my day!";

s.match(/yes.*day/);
// Returns null

s.match(/yes[^]*day/);
// Returns ["yes\nmake my day"]
```




 
### Using a regular expression with the sticky flag 

 
The [`sticky`](regexp/sticky) flag indicates that the regular expression
performs sticky matching in the target string by attempting to match
starting at [`RegExp.prototype.lastIndex`](regexp/lastindex).

 
 
[js]


```js
const str = "#foo#";
const regex = /foo/y;

regex.lastIndex = 1;
regex.test(str); // true
regex.lastIndex = 5;
regex.test(str); // false (lastIndex is taken into account with sticky flag)
regex.lastIndex; // 0 (reset after match failure)
```




 
### The difference between the sticky flag and the global flag 

 
With the sticky flag `y`, the next match has to happen at the
`lastIndex` position, while with the global flag `g`, the match can
happen at the `lastIndex` position or later:

 
 
[js]


```js
const re = /\d/y;
let r;
while ((r = re.exec("123 456"))) {
  console.log(r, "AND re.lastIndex", re.lastIndex);
}

// [ '1', index: 0, input: '123 456', groups: undefined ] AND re.lastIndex 1
// [ '2', index: 1, input: '123 456', groups: undefined ] AND re.lastIndex 2
// [ '3', index: 2, input: '123 456', groups: undefined ] AND re.lastIndex 3
//  … and no more match.
```


With the global flag `g`, all 6 digits would be matched, not just 3.



 
### Regular expression and Unicode characters 

 
`\w` and `\W` only matches ASCII based characters; for example, `a` to
`z`, `A` to `Z`, `0` to `9`, and `_`.

To match characters from other languages such as Cyrillic or Hebrew, use
`\uhhhh`, where `hhhh` is the character\'s Unicode value in hexadecimal.

This example demonstrates how one can separate out Unicode characters
from a word.

 
 
[js]


```js
const text = "Образец text на русском языке";
const regex = /[\u0400-\u04FF]+/g;

const match = regex.exec(text);
console.log(match[0]); // 'Образец'
console.log(regex.lastIndex); // 7

const match2 = regex.exec(text);
console.log(match2[0]); // 'на' (did not log 'text')
console.log(regex.lastIndex); // 15

// and so on
```


The [Unicode property
escapes](../regular_expressions/unicode_character_class_escape) feature
provides a simpler way to target particular Unicode ranges, by allowing
for statements like `\p{scx=Cyrl}` (to match any Cyrillic letter), or
`\p{L}/u` (to match a letter from any language).



 
### Extracting subdomain name from URL 

 
 
 
[js]


```js
const url = "http://xxx.domain.com";
console.log(/^https?:\/\/(.+?)\./.exec(url)[1]); // 'xxx'
```


 
**Note:** Instead of using regular expressions for parsing URLs, it is
usually better to use the browsers built-in URL parser by using the [URL
API](https://developer.mozilla.org/en-US/docs/Web/API/URL_API).




 
### Building a regular expression from dynamic inputs 

 
 
 
[js]


```js
const breakfasts = ["bacon", "eggs", "oatmeal", "toast", "cereal"];
const order = "Let me get some bacon and eggs, please";

order.match(new RegExp(`\\b(${breakfasts.join("|")})\\b`, "g"));
// Returns ['bacon', 'eggs']
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp-regular-expression-objects]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp-regular-expression-objects)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

`@@species`

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

6.5.0

`@@split`

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

`RegExp`

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

`RegExp`

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

`compile`

1

12

1

6

3.1

18

4

10.1

2

1.0

4.4

1.0

0.10.0

`dotAll`

62

79

78

49

11.1

62

79

46

11.3

8.0

62

1.0

8.10.0

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

`flags`

49

79

37

39

9

49

37

41

9

5.0

49

1.0

6.0.0

`global`

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

`hasIndices`

90

90

88

76

15

90

88

64

15

15.0

90

1.8

16.0.0

`ignoreCase`

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

`input`

1

12

1

15

3

18

4

14

1

1.0

4.4

1.0

0.10.0

`lastIndex`

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

`lastMatch`

1

12

1

10.5

3

18

4

11

1

1.0

4.4

1.0

0.10.0

`lastParen`

1

12

1

10.5

3

18

4

11

1

1.0

4.4

1.0

0.10.0

`leftContext`

1

12

1

8

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`multiline`

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

`n`

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

`rightContext`

1

12

1

8

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`source`

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

`sticky`

49

13

3

36

10

49

4

36

10

5.0

49

1.0

6.0.0

`test`

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

`toString`

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

`unicode`

50

12Case folding is implemented in version 13

46

37

10

50

46

37

10

5.0

50

1.0

6.0.0Case folding is implemented in version 8.6.0

`unicodeSets`

112

112

116

98

17

112

116

75

17

23.0

112

1.32

20.0.0

 
### Firefox-specific notes 

 
Starting with Firefox 34, in the case of a capturing group with
quantifiers preventing its exercise, the matched text for a capturing
group is now `undefined` instead of an empty string:

 
 
[js]


```js
// Firefox 33 or older
"x".replace(/x(.)?/g, (m, group) => {
  console.log(`group: ${JSON.stringify(group)}`);
});
// group: ""

// Firefox 34 or newer
"x".replace(/x(.)?/g, (m, group) => {
  console.log(`group: ${group}`);
});
// group: undefined
```


Note that due to web compatibility, `RegExp.$N` will still return an
empty string instead of `undefined` ([bug
1053944](https://bugzil.la/1053944)).



 
See also 
--------

 
-   [Polyfill of many modern `RegExp` features (`dotAll`, `sticky`
    flags, named capture groups, etc.) in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [Regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    guide
-   [Regular expressions](../regular_expressions)
-   [`String.prototype.match()`](string/match)
-   [`String.prototype.replace()`](string/replace)
-   [`String.prototype.split()`](string/split)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp>

