SyntaxError: cannot use \`??\` unparenthesized within \`\|\|\` and \`&&\` expressions
=====================================================================================


The JavaScript exception \"cannot use `??` unparenthesized within `||`
and `&&` expressions\" occurs when an [nullish coalescing
operator](../operators/nullish_coalescing) is used with a [logical
OR](../operators/logical_or) or [logical AND](../operators/logical_and)
in the same expression without parentheses.



Message
-------


```text
SyntaxError: Unexpected token '??' (V8-based)
SyntaxError: cannot use `??` unparenthesized within `||` and `&&` expressions (Firefox)
SyntaxError: Unexpected token '??'. Coalescing and logical operators used together in the same expression; parentheses must be used to disambiguate. (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror)




What went wrong? 
----------------


The [operator precedence](../operators/operator_precedence) chain looks
like this:

```text
|   >   &&   >   ||   >   =
|   >   ??   >   =
```

However, the precedence *between* `??` and `&&`/`||` is intentionally
undefined, because the short circuiting behavior of logical operators
can make the expression\'s evaluation counter-intuitive. Therefore, the
following combinations are all syntax errors, because the language
doesn\'t know how to parenthesize the operands:



[js]


```js
a ?? b || c;
a || b ?? c;
a ?? b && c;
a && b ?? c;
```


Instead, make your intent clear by parenthesizing either side
explicitly:



[js]


```js
(a ?? b) || c;
a ?? (b && c);
```





Examples
--------


When migrating legacy code that uses `||` and `&&` for guarding against
`null` or `undefined`, you may often convert it partially:



[js]


```js
function getId(user, fallback) {
  // Previously: user && user.id || fallback
  return user && user.id ?? fallback; // SyntaxError: cannot use `??` unparenthesized within `||` and `&&` expressions
}
```


Instead, consider parenthesizing the `&&`:



[js]


```js
function getId(user, fallback) {
  return (user && user.id) ?? fallback;
}
```


Even better, consider using [optional
chaining](../operators/optional_chaining) instead of `&&`:



[js]


```js
function getId(user, fallback) {
  return user?.id ?? fallback;
}
```





See also 
--------


-   [Issue about nullish coalescing
    precedence](https://github.com/tc39/proposal-nullish-coalescing/issues/15)
    in the TC39 nullish-coalescing proposal
-   [Nullish coalescing operator
    (`??`)](../operators/nullish_coalescing)
-   [Operator precedence](../operators/operator_precedence)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_use_nullish_coalescing_unparenthesized>

