RegExp.prototype.source
=======================

 
The `source` accessor property of [`RegExp`](../regexp) instances
returns a string containing the source text of this regular expression,
without the two forward slashes on both sides or any flags.


 
Try it 
------

 



 
Description
-----------

 
Conceptually, the `source` property is the text between the two forward
slashes in the regular expression literal. The language requires the
returned string to be properly escaped, so that when the `source` is
concatenated with a forward slash on both ends, it would form a parsable
regex literal. For example, for `new RegExp("/")`, the `source` is
`\\/`, because if it generates `/`, the resulting literal becomes `///`,
which is a line comment. Similarly, all [line
terminators](../../lexical_grammar#line_terminators) will be escaped
because line terminator *characters* would break up the regex literal.
There\'s no requirement for other characters, as long as the result is
parsable. For empty regular expressions, the string `(?:)` is returned.



 
Examples
--------


 
### Using source 

 
 
 
[js]


```js
const regex = /fooBar/gi;

console.log(regex.source); // "fooBar", doesn't contain /.../ and "gi".
```




 
### Empty regular expressions and escaping 

 
 
 
[js]


```js
new RegExp().source; // "(?:)"

new RegExp("\n").source === "\\n"; // true, starting with ES5
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.source]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.source)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`empty_regex_string`

6

12

38

15

5

18

38

14

4.2

1.0

≤37

1.0

0.10.0

`escaping`

73

12

38

60

6

73

38

52

6

11.0

73

1.0

12.0.0

`prototype_accessor`

48

12

41

35

1.3

48

41

35

1

5.0

48

1.0

6.0.0

 
See also 
--------

 
-   [`RegExp.prototype.flags`](flags)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/source>

