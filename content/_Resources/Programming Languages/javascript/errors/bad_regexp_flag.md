SyntaxError: invalid regular expression flag \"x\"
==================================================


The JavaScript exception \"invalid regular expression flag\" occurs when
the flags in a regular expression contain any flag that is not one of:
`d`, `g`, `i`, `m`, `s`, `u`, `v`, or `y`.

It may also be raised if the expression contains more than one instance
of a valid flag.



Message
-------


```text
SyntaxError: Invalid regular expression flags (V8-based)
SyntaxError: invalid regular expression flag x (Firefox)
SyntaxError: Invalid regular expression: invalid flags (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror)




What went wrong? 
----------------


The regular expression contains invalid flags, or valid flags have been
used more than once in the expression.

The valid (allowed) flags are `d`, `g`, `i`, `m`, `s`, `u`, `v`, and
`y`. They are introduced in more detail in [Regular expressions \>
Advanced searching with
flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags).




Examples
--------


In a regular expression literal, which consists of a pattern enclosed
between slashes, the flags are defined after the second slash. Regular
expression flags can be used separately or together in any order. This
syntax shows how to declare the flags using the regular expression
literal:



[js]


```js
const re = /pattern/flags;
```


They can also be defined in the constructor function of the
[`RegExp`](../global_objects/regexp) object (second parameter):



[js]


```js
const re = new RegExp("pattern", "flags");
```


Here is an example showing use of only correct flags.



[js]


```js
/foo/g;
/foo/gims;
/foo/uy;
```


Below is an example showing the use of some invalid flags `b`, `a` and
`r`:



[js]


```js
/foo/bar;

// SyntaxError: invalid regular expression flag "b"
```


The code below is incorrect, because `W`, `e` and `b` are not valid
flags.



[js]


```js
const obj = {
  url: /docs/Web,
};

// SyntaxError: invalid regular expression flag "W"
```


An expression containing two slashes is interpreted as a regular
expression literal. Most likely the intent was to create a string
literal, using single or double quotes as shown below:



[js]


```js
const obj = {
  url: "/docs/Web",
};
```





See also 
--------


-   [Regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    guide




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_regexp_flag>

