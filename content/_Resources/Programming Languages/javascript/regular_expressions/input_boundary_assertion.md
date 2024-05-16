Input boundary assertion: \^, \$
================================

 
An **input boundary assertion** checks if the current position in the
string is an input boundary. An input boundary is the start or end of
the string; or, if the `m` flag is set, the start or end of a line.


 
Syntax
------

 
 
 
[regex]


```regex
^
$
```




 
Description
-----------

 
`^` asserts that the current position is the start of input. `$` asserts
that the current position is the end of input. Both are *assertions*, so
they don\'t consume any characters.

More precisely, `^` asserts that the character to the left is out of
bounds of the string; `$` asserts that the character to the right is out
of bounds of the string. If the
[`m`](../global_objects/regexp/multiline) flag is set, `^` also matches
if the character to the left is a [line
terminator](../lexical_grammar#line_terminators) character, and `$` also
matches if the character to the right is a line terminator.

Unless the `m` flag is set, the `^` and `$` assertions only make sense
when placed at the boundaries of the pattern, because any other
characters to the left or right of them would necessarily cause the
assertion to fail.

The `y` flag doesn\'t change the meaning of these assertions --- see
also [anchored sticky
flag](../global_objects/regexp/sticky#anchored_sticky_flag).



 
Examples
--------


 
### Removing trailing slashes 

 
The following example removes trailing slashes from a URL string:

 
 
[js]


```js
function removeTrailingSlash(url) {
  return url.replace(/\/$/, "");
}

removeTrailingSlash("https://example.com/"); // "https://example.com"
removeTrailingSlash("https://example.com/docs/"); // "https://example.com/docs"
```




 
### Matching file extensions 

 
The following example checks file types by matching the file extension,
which always comes at the end of the string:

 
 
[js]


```js
function isImage(filename) {
  return /\.(?:png|jpe?g|webp|avif|gif)$/i.test(filename);
}

isImage("image.png"); // true
isImage("image.jpg"); // true
isImage("image.pdf"); // false
```




 
### Matching entire input 

 
Sometimes you want to make sure that your regex matches the entire
input, not just a substring of the input. For example, if you are
determining if a string is a valid
[identifier](../lexical_grammar#identifiers), you can add input boundary
assertions to both ends of the pattern:

 
 
[js]


```js
function isValidIdentifier(str) {
  return /^[$_\p{ID_Start}][$_\p{ID_Continue}]*$/u.test(str);
}

isValidIdentifier("foo"); // true
isValidIdentifier("$1"); // true
isValidIdentifier("1foo"); // false
isValidIdentifier("  foo  "); // false
```


This function is useful when doing codegen (generating code using code),
because you can use valid identifiers differently from other string
properties, such as [dot
notation](../operators/property_accessors#dot_notation) instead of
[bracket notation](../operators/property_accessors#bracket_notation):

 
 
[js]


```js
const variables = ["foo", "foo:bar", "  foo  "];

function toAssignment(key) {
  if (isValidIdentifier(key)) {
    return `globalThis.${key} = undefined;`;
  }
  // JSON.stringify() escapes quotes and other special characters
  return `globalThis[${JSON.stringify(key)}] = undefined;`;
}

const statements = variables.map(toAssignment).join("\n");

console.log(statements);
// globalThis.foo = undefined;
// globalThis["foo:bar"] = undefined;
// globalThis["  foo  "] = undefined;
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-Assertion]](https://tc39.es/ecma262/multipage/text-processing.html#prod-Assertion)

  -------------------------------------------------------------------------------------------------


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

`Input_boundary_assertion`

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

 
-   [Assertions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Assertions)
    guide
-   [Regular expressions](../regular_expressions)
-   [Word boundary assertion: `\b`, `\B`](word_boundary_assertion)
-   [Lookahead assertion: `(?=...)`, `(?!...)`](lookahead_assertion)
-   [Lookbehind assertion: `(?<=...)`, `(?<!...)`](lookbehind_assertion)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Input_boundary_assertion>

