RegExp.\$1, ..., RegExp.\$9
===========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Note:** All `RegExp` static properties that expose the last match
state globally are deprecated. See [deprecated RegExp
features](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#regexp)
for more information.


The `RegExp.$1, …, RegExp.$9` static accessor properties return
parenthesized substring matches.


 
Description
-----------

 
Because `$1`--`$9` are static properties of [`RegExp`](../regexp), you
always use them as `RegExp.$1`, `RegExp.$2`, etc., rather than as
properties of a `RegExp` object you created.

The values of `$1, …, $9` update whenever a `RegExp` (but not a `RegExp`
subclass) instance makes a successful match. If no matches have been
made, or if the last match does not have the corresponding capturing
group, the respective property is an empty string. The set accessor of
each property is `undefined`, so you cannot change the properties
directly.

The number of possible parenthesized substrings is unlimited, but the
`RegExp` object can only hold the first nine. You can access all
parenthesized substrings through the returned array\'s indexes.

`$1, …, $9` can also be used in the replacement string of
[`String.prototype.replace()`](../string/replace), but that\'s unrelated
to the `RegExp.$n` legacy properties.



 
Examples
--------


 
### Using \$n with RegExp.prototype.test() 

 
The following script uses the [`RegExp.prototype.test()`](test) method
to grab a number in a generic string.

 
 
[js]


```js
const str = "Test 24";
const number = /(\d+)/.test(str) ? RegExp.$1 : "0";
number; // "24"
```


Please note that any operation involving the usage of other regular
expressions between a `re.test(str)` call and the `RegExp.$n` property,
might have side effects, so that accessing these special properties
should be done instantly, otherwise the result might be unexpected.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Legacy RegExp features\
  [\#
  additional-properties-of-the-regexp-constructor]](https://github.com/tc39/proposal-regexp-legacy-features/#additional-properties-of-the-regexp-constructor)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`RegExp.input ($_)`](input)
-   [`RegExp.lastMatch ($&)`](lastmatch)
-   [`RegExp.lastParen ($+)`](lastparen)
-   [`` RegExp.leftContext ($`) ``](leftcontext)
-   [`RegExp.rightContext ($')`](rightcontext)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/n>

