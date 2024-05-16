Addition (+)
============

 
The `+` operator produces the sum of numeric operands or string
concatenation.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x + y
```




 
Description
-----------

 
The `+` operator is overloaded for two distinct operations: numeric
addition and string concatenation. When evaluating, it first [coerces
both operands to
primitives](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion).
Then, the two operands\' types are tested:

-   If one side is a string, the other operand is also [converted to a
    string](../global_objects/string#string_coercion) and they are
    concatenated.
-   If they are both [BigInts](../global_objects/bigint), BigInt
    addition is performed. If one side is a BigInt but the other is not,
    a [`TypeError`](../global_objects/typeerror) is thrown.
-   Otherwise, both sides are [converted to
    numbers](../global_objects/number#number_coercion), and numeric
    addition is performed.

String concatenation is often thought to be equivalent with [template
literals](../template_literals) or
[`String.prototype.concat()`](../global_objects/string/concat), but they
are not. Addition coerces the expression to a *primitive*, which calls
[`valueOf()`](../global_objects/object/valueof) in priority; on the
other hand, template literals and `concat()` coerce the expression to a
*string*, which calls [`toString()`](../global_objects/object/tostring)
in priority. If the expression has a
[`@@toPrimitive`](../global_objects/symbol/toprimitive) method, string
concatenation calls it with `"default"` as hint, while template literals
use `"string"`. This is important for objects that have different string
and primitive representations --- such as
[Temporal](https://github.com/tc39/proposal-temporal), whose `valueOf()`
method throws.

 
 
[js]


```js
const t = Temporal.Now.instant();
"" + t; // Throws TypeError
`${t}`; // '2022-07-31T04:48:56.113918308Z'
"".concat(t); // '2022-07-31T04:48:56.113918308Z'
```


You are advised to not use `"" + x` to perform [string
coercion](../global_objects/string#string_coercion).



 
Examples
--------


 
### Number addition 

 
 
 
[js]


```js
// Number + Number -> addition
1 + 2; // 3

// Boolean + Number -> addition
true + 1; // 2

// Boolean + Boolean -> addition
false + false; // 0
```




 
### BigInt addition 

 
 
 
[js]


```js
// BigInt + BigInt -> addition
1n + 2n; // 3n

// BigInt + Number -> throws TypeError
1n + 2; // TypeError: Cannot mix BigInt and other types, use explicit conversions

// To add a BigInt to a non-BigInt, convert either operand
1n + BigInt(2); // 3n
Number(1n) + 2; // 3
```




 
### String concatenation 

 
 
 
[js]


```js
// String + String -> concatenation
"foo" + "bar"; // "foobar"

// Number + String -> concatenation
5 + "foo"; // "5foo"

// String + Boolean -> concatenation
"foo" + false; // "foofalse"

// String + Number -> concatenation
"2" + 2; // "22"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-addition-operator-plus]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-addition-operator-plus)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

`Addition`

1

12

1

3

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

 
-   [Subtraction (`-`)](subtraction)
-   [Division (`/`)](division)
-   [Multiplication (`*`)](multiplication)
-   [Remainder (`%`)](remainder)
-   [Exponentiation (`**`)](exponentiation)
-   [Increment (`++`)](increment)
-   [Decrement (`--`)](decrement)
-   [Unary negation (`-`)](unary_negation)
-   [Unary plus (`+`)](unary_plus)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition>

