Logical AND (&&)
================

 
The `&&` (logical conjunction) operator for a set of boolean operands
will be `true` if and only if all the operands are `true`. Otherwise it
will be `false`.

More generally, the operator returns the value of the first
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) operand
encountered when evaluating from left to right, or the value of the last
operand if they are all
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x && y
```




 
Description
-----------

 
Logical AND (`&&`) evaluates operands from left to right, returning
immediately with the value of the first
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) operand
it encounters; if all values are
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy), the
value of the last operand is returned.

If a value can be converted to `true`, the value is so-called
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy). If a
value can be converted to `false`, the value is so-called
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).

Examples of expressions that can be converted to false are:

-   `false`;
-   `null`;
-   `NaN`;
-   `0`;
-   empty string (`""` or `''` or ``` `` ```);
-   `undefined`.

The AND operator preserves non-Boolean values and returns them as they
are:

 
 
[js]


```js
result = "" && "foo"; // result is assigned "" (empty string)
result = 2 && 0; // result is assigned 0
result = "foo" && 4; // result is assigned 4
```


Even though the `&&` operator can be used with non-Boolean operands, it
is still considered a boolean operator since its return value can always
be converted to a [boolean
primitive](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#boolean_type).
To explicitly convert its return value (or any expression in general) to
the corresponding boolean value, use a double
[`NOT operator`](logical_not) or the
[`Boolean`](../global_objects/boolean/boolean) constructor.



 
### Short-circuit evaluation 

 
The logical AND expression is a short-circuit operator. As each operand
is converted to a boolean, if the result of one conversion is found to
be `false`, the AND operator stops and returns the original value of
that falsy operand; it does **not** evaluate any of the remaining
operands.

Consider the pseudocode below.

```text
(some falsy expression) && expr
```

The `expr` part is **never evaluated** because the first operand
`(some falsy expression)` is evaluated as
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy). If
`expr` is a function, the function is never called. See the example
below:

 
 
[js]


```js
function A() {
  console.log("called A");
  return false;
}
function B() {
  console.log("called B");
  return true;
}

console.log(A() && B());
// Logs "called A" to the console due to the call for function A,
// && evaluates to false (function A returns false), then false is logged to the console;
// the AND operator short-circuits here and ignores function B
```




 
### Operator precedence 

 
The AND operator has a higher precedence than the OR operator, meaning
the `&&` operator is executed before the `||` operator (see [operator
precedence](operator_precedence)).

 
 
[js]


```js
true || false && false; // true
true && (false || false); // false
(2 === 3) || (4 < 0) && (1 === 1); // false
```




 
Examples
--------


 
### Using AND 

 
The following code shows examples of the `&&` (logical AND) operator.

 
 
[js]


```js
a1 = true && true; // t && t returns true
a2 = true && false; // t && f returns false
a3 = false && true; // f && t returns false
a4 = false && 3 === 4; // f && f returns false
a5 = "Cat" && "Dog"; // t && t returns "Dog"
a6 = false && "Cat"; // f && t returns false
a7 = "Cat" && false; // t && f returns false
a8 = "" && false; // f && f returns ""
a9 = false && ""; // f && f returns false
```




 
### Conversion rules for booleans 

 
#### Converting AND to OR 

The following operation involving **booleans**:

 
 
[js]


```js
bCondition1 && bCondition2
```


is always equal to:

 
 
[js]


```js
!(!bCondition1 || !bCondition2)
```


#### Converting OR to AND 

The following operation involving **booleans**:

 
 
[js]


```js
bCondition1 || bCondition2
```


is always equal to:

 
 
[js]


```js
!(!bCondition1 && !bCondition2)
```




 
### Removing nested parentheses 

 
As logical expressions are evaluated left to right, it is always
possible to remove parentheses from a complex expression provided that
certain rules are followed.

The following composite operation involving **booleans**:

 
 
[js]


```js
bCondition1 || (bCondition2 && bCondition3)
```


is always equal to:

 
 
[js]


```js
bCondition1 || bCondition2 && bCondition3
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-LogicalANDExpression]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-LogicalANDExpression)

  ---------------------------------------------------------------------------------------------------------------------------------------


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

`Logical_AND`

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

 
-   [`Boolean`](../global_objects/boolean)
-   [Truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
-   [Falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND>

