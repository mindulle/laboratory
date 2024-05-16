Named backreference: \\k\<name\>
================================

 
A **named backreference** refers to the submatch of a previous [named
capturing group](named_capturing_group) and matches the same text as
that group. For [unnamed capturing groups](capturing_group), you need to
use the normal [backreference](backreference) syntax.


 
Syntax
------

 
 
 
[regex]


```regex
\k<name>
```




 
### Parameters

 

[`name`](#name)

:   The name of the group. Must be a valid
    [identifier](../lexical_grammar#identifiers) and refer to an
    existent named capturing group.



 
Description
-----------

 
Named backreferences are very similar to normal backreferences: it
refers to the text matched by a capturing group and matches the same
text. The difference is that you refer to the capturing group by name
instead of by number. This makes the regular expression more readable
and easier to refactor and maintain.

In [Unicode-unaware
mode](../global_objects/regexp/unicode#unicode-aware_mode), the sequence
`\k` only starts a named backreference if the regex contains at least
one named capturing group. Otherwise, it is an [identity
escape](character_escape) and is the same as the literal character `k`.
This is a [deprecated syntax for web
compatibility](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#regexp),
and you should not rely on it.

 
 
[js]


```js
/\k/.test("k"); // true
```




 
Examples
--------


 
### Pairing quotes 

 
The following function matches the `title='xxx'` and `title="xxx"`
patterns in a string. To ensure the quotes match, we use a backreference
to refer to the first quote. Accessing the second capturing group
(`[2]`) returns the string between the matching quote characters:

 
 
[js]


```js
function parseTitle(metastring) {
  return metastring.match(/title=(?<quote>["'])(.*?)\k<quote>/)[2];
}

parseTitle('title="foo"'); // 'foo'
parseTitle("title='foo' lang='en'"); // 'foo'
parseTitle('title="Named capturing groups\' advantages"'); // "Named capturing groups' advantages"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-AtomEscape]](https://tc39.es/ecma262/multipage/text-processing.html#prod-AtomEscape)

  ---------------------------------------------------------------------------------------------------


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

`Named_backreference`

64

79

78

51

11.1

64

79

47

11.3

9.0

64

1.0

10.0.0

 
See also 
--------

 
-   [Groups and
    backreferences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences)
    guide
-   [Regular expressions](../regular_expressions)
-   [Capturing group: `(...)`](capturing_group)
-   [Named capturing group: `(?<name>...)`](named_capturing_group)
-   [Backreference: `\1`, `\2`](backreference)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Named_backreference>

