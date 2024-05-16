Logical NOT (!)
===============

 
The `!` (logical complement, negation) operator takes truth to falsity
and vice versa. It is typically used with boolean (logical) values. When
used with non-Boolean values, it returns `false` if its single operand
can be converted to `true`; otherwise, returns `true`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
!x
```




 
Description
-----------

 
Returns `false` if its single operand can be converted to `true`;
otherwise, returns `true`.

If a value can be converted to `true`, the value is so-called
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy). If a
value can be converted to `false`, the value is so-called
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).

Examples of expressions that can be converted to false are:

-   `null`;
-   `NaN`;
-   `0`;
-   empty string (`""` or `''` or ``` `` ```);
-   `undefined`.

Even though the `!` operator can be used with operands that are not
Boolean values, it can still be considered a boolean operator since its
return value can always be converted to a [boolean
primitive](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#boolean_type).
To explicitly convert its return value (or any expression in general) to
the corresponding boolean value, use a double NOT operator (`!!`) or the
[`Boolean`](../global_objects/boolean/boolean) constructor.



 
Examples
--------


 
### Using NOT 

 
The following code shows examples of the `!` (logical NOT) operator.

 
 
[js]


```js
!true; // !t returns false
!false; // !f returns true
!""; // !f returns true
!"Cat"; // !t returns false
```




 
### Double NOT (`!!`) 

 
It is possible to use a couple of NOT operators in series to explicitly
force the conversion of any value to the corresponding [boolean
primitive](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#boolean_type).
The conversion is based on the \"truthyness\" or \"falsyness\" of the
value (see
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) and
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)).

The same conversion can be done through the
[`Boolean()`](../global_objects/boolean/boolean) function.

 
 
[js]


```js
!!true; // !!truthy returns true
!!{}; // !!truthy returns true: any object is truthy...
!!new Boolean(false); // ...even Boolean objects with a false .valueOf()!
!!false; // !!falsy returns false
!!""; // !!falsy returns false
!!Boolean(false); // !!falsy returns false
```




 
### Converting between NOTs 

 
The following operation involving **booleans**:

 
 
[js]


```js
!!bCondition
```


is always equal to:

 
 
[js]


```js
bCondition
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-logical-not-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-logical-not-operator)

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

`Logical_NOT`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT>

