Wildcard: .
===========

 
A **wildcard** matches all characters except line terminators. It also
matches line terminators if the `s` flag is set.


 
Syntax
------

 
 
 
[regex]


```regex
.
```




 
Description
-----------

 
`.` matches any character except [line
terminators](../lexical_grammar#line_terminators). If the
[`s`](../global_objects/regexp/dotall) flag is set, `.` also matches
line terminators.

The exact character set matched by `.` depends on whether the regex is
[Unicode-aware](../global_objects/regexp/unicode#unicode-aware_mode). If
it is Unicode-aware, `.` matches any Unicode code point; otherwise, it
matches any UTF-16 code unit. For example:

 
 
[js]


```js
/../.test("😄"); // true; matches two UTF-16 code units as a surrogate pair
/../u.test("😄"); // false; input only has one Unicode character
```




 
Examples
--------


 
### Usage with quantifiers 

 
Wildcards are often used with [quantifiers](quantifier) to match any
character sequence, until the next character of interest is found. For
example, the following example extracts the title of a Markdown page in
the form `# Title`:

 
 
[js]


```js
function parseTitle(entry) {
  // Use multiline mode because the title may not be at the start of
  // the file. Note that the m flag does not make . match line
  // terminators, so the title must be on a single line
  // Return text matched by the first capturing group.
  return /^#[ \t]+(.+)$/m.exec(entry)?.[1];
}

parseTitle("# Hello world"); // "Hello world"
parseTitle("## Subsection"); // undefined
parseTitle(`
---
slug: Web/JavaScript/Reference/Regular_expressions/Wildcard
---

# Wildcard: .

A **wildcard** matches all characters except line terminators.
`); // "Wildcard: ."
```




 
### Matching code block content 

 
The following example matches the content of a code block enclosed by
three backticks in Markdown. It uses the `s` flag to make `.` match line
terminators, because the content of a code block may span multiple
lines:

 
 
[js]


```js
function parseCodeBlock(entry) {
  return /^```.*?^(.+?)\n```/ms.exec(entry)?.[1];
}

parseCodeBlock(`
\`\`\`js
console.log("Hello world");
\`\`\`
`); // "console.log("Hello world");"

parseCodeBlock(`
A \`try...catch\` statement must have the blocks enclosed in curly braces.

\`\`\`js example-bad
try
  doSomething();
catch (e)
  console.log(e);
\`\`\`
`); // "try\n  doSomething();\ncatch (e)\n  console.log(e);"
```


 
**Warning:** These examples are for demonstration only. If you want to
parse Markdown, use a dedicated Markdown parser because there are many
edge cases to consider.




Specifications
--------------

 
  ---------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-Atom]](https://tc39.es/ecma262/multipage/text-processing.html#prod-Atom)

  ---------------------------------------------------------------------------------------


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

`Wildcard`

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

 
-   [Character
    classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Character_classes)
    guide
-   [Regular expressions](../regular_expressions)
-   [Character class: `[...]`, `[^...]`](character_class)
-   [Character class escape: `\d`, `\D`, `\w`, `\W`, `\s`,
    `\S`](character_class_escape)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Wildcard>

