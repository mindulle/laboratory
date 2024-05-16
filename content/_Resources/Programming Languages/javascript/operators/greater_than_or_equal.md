Greater than or equal (\>=)
===========================

 
The `>=` operator returns `true` if the left operand is greater than or
equal to the right operand, and `false` otherwise.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x >= y
```




 
Description
-----------

 
The operands are compared using the same algorithm as the [Less
than](less_than) operator, with the result negated. `x >= y` is
generally equivalent to `!(x < y)`, except for two cases where `x >= y`
and `x < y` are both `false`:

-   If one of the operands gets converted to a BigInt, while the other
    gets converted to a string that cannot be converted to a BigInt
    value (it throws a [syntax error](../errors/invalid_bigint_syntax)
    when passed to [`BigInt()`](../global_objects/bigint/bigint)).
-   If one of the operands gets converted to `NaN`. (For example,
    strings that cannot be converted to numbers, or `undefined`.)

`x >= y` is generally equivalent to `x > y || x == y`, except for a few
cases:

-   When one of `x` or `y` is `null`, and the other is something that\'s
    not `null` and becomes 0 when [coerced to
    numeric](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
    (including `0`, `0n`, `false`, `""`, `"0"`, `new Date(0)`, etc.):
    `x >= y` is `true`, while `x > y || x == y` is `false`.
-   When one of `x` or `y` is `undefined`, and the other is one of
    `null` or `undefined`: `x >= y` is `false`, while `x == y` is
    `true`.
-   When `x` and `y` are the same object that becomes `NaN` after the
    first step of [Less than](less_than) (such as `new Date(NaN)`):
    `x >= y` is `false`, while `x == y` is `true`.
-   When `x` and `y` are different objects that become the same value
    after the first step of [Less than](less_than): `x >= y` is `true`,
    while `x > y || x == y` is `false`.



 
Examples
--------


 
### String to string comparison 

 
 
 
[js]


```js
"a" >= "b"; // false
"a" >= "a"; // true
"a" >= "3"; // true
```




 
### String to number comparison 

 
 
 
[js]


```js
"5" >= 3; // true
"3" >= 3; // true
"3" >= 5; // false

"hello" >= 5; // false
5 >= "hello"; // false
```




 
### Number to Number comparison 

 
 
 
[js]


```js
5 >= 3; // true
3 >= 3; // true
3 >= 5; // false
```




 
### Number to BigInt comparison 

 
 
 
[js]


```js
5n >= 3; // true
3 >= 3n; // true
3 >= 5n; // false
```




 
### Comparing Boolean, null, undefined, NaN 

 
 
 
[js]


```js
true >= false; // true
true >= true; // true
false >= true; // false

true >= 0; // true
true >= 1; // true

null >= 0; // true
1 >= null; // true

undefined >= 3; // false
3 >= undefined; // false

3 >= NaN; // false
NaN >= 3; // false
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-relational-operators]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-relational-operators)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`Greater_than_or_equal`

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

 
-   [Greater than (`>`)](greater_than)
-   [Less than (`<`)](less_than)
-   [Less than or equal (`<=`)](less_than_or_equal)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than_or_equal>

