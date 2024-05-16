Disjunction: \|
===============

 
A **disjunction** specifies multiple alternatives. Any alternative
matching the input causes the entire disjunction to be matched.


 
Syntax
------

 
 
 
[regex]


```regex
alternative1|alternative2
alternative1|alternative2|alternative3|…
```




 
### Parameters

 

[`alternativeN`](#alternativen)

:   One alternative pattern, composed of a sequence of [atoms and
    assertions](../regular_expressions#assertions). Successfully
    matching one alternative causes the entire disjunction to be
    matched.



 
Description
-----------

 
The `|` regular expression operator separates two or more
*alternatives*. The pattern first tries to match the first alternative;
if it fails, it tries to match the second one, and so on. For example,
the following matches `"a"` instead of `"ab"`, because the first
alternative already matches successfully:

 
 
[js]


```js
/a|ab/.exec("abc"); // ['a']
```


The `|` operator has the lowest precedence in a regular expression. If
you want to use a disjunction as a part of a bigger pattern, you must
[group](non-capturing_group) it.

When a grouped disjunction has more expressions after it, the matching
begins by selecting the first alternative and attempting to match the
rest of the regular expression. If the rest of the regular expression
fails to match, the matcher tries the next alternative instead. For
example,

 
 
[js]


```js
/(?:(a)|(ab))(?:(c)|(bc))/.exec("abc"); // ['abc', 'a', undefined, undefined, 'bc']
// Not ['abc', undefined, 'ab', 'c', undefined]
```


This is because by selecting `a` in the first alternative, it\'s
possible to select `bc` in the second alternative and result in a
successful match. This process is called *backtracking*, because the
matcher first goes beyond the disjunction and then comes back to it when
subsequent matching fails.

Note also that any capturing parentheses inside an alternative that\'s
not matched produce `undefined` in the resulting array.

An alternative can be empty, in which case it matches the empty string
(in other words, always matches).

Alternatives are always attempted left-to-right, regardless of the
direction of matching (which is reversed in a
[lookbehind](lookbehind_assertion)).



 
Examples
--------


 
### Matching file extensions 

 
The following example matches file extensions, using the same code as
the [input boundary
assertion](input_boundary_assertion#matching_file_extensions) article:

 
 
[js]


```js
function isImage(filename) {
  return /\.(?:png|jpe?g|webp|avif|gif)$/i.test(filename);
}

isImage("image.png"); // true
isImage("image.jpg"); // true
isImage("image.pdf"); // false
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-Disjunction]](https://tc39.es/ecma262/multipage/text-processing.html#prod-Disjunction)

  -----------------------------------------------------------------------------------------------------


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

`Disjunction`

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
-   [Quantifier: `*`, `+`, `?`, `{n}`, `{n,}`, `{n,m}`](quantifier)
-   [Character class: `[...]`, `[^...]`](character_class)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Disjunction>

