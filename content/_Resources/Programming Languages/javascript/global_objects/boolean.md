Boolean
=======

 
The `Boolean` object represents a truth value: `true` or `false`.


 
Description
-----------


 
### Boolean primitives and Boolean objects 

 
Do not confuse the
[primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive)
`Boolean` values `true` and `false` with the `true` and `false` values
of the `Boolean` object.

**Any** object, including a `Boolean` object whose value is `false`,
evaluates to `true` when passed to a conditional statement. For example,
the condition in the following [`if`](../statements/if...else) statement
evaluates to `true`:

 
 
[js]


```js
const x = new Boolean(false);
if (x) {
  // this code is executed
}
```


This behavior does not apply to `Boolean` primitives. For example, the
condition in the following [`if`](../statements/if...else) statement
evaluates to `false`:

 
 
[js]


```js
const x = false;
if (x) {
  // this code is not executed
}
```


Do not use the `Boolean()` constructor with `new` to convert a
non-boolean value to a boolean value --- use `Boolean` as a function or
a [double NOT](../operators/logical_not#double_not_!!) instead:

 
 
[js]


```js
const good = Boolean(expression); // use this
const good2 = !!expression; // or this
const bad = new Boolean(expression); // don't use this!
```


If you specify any object, including a `Boolean` object whose value is
`false`, as the initial value of a `Boolean` object, the new `Boolean`
object has a value of `true`.

 
 
[js]


```js
const myFalse = new Boolean(false); // initial value of false
const g = Boolean(myFalse); // initial value of true
const myString = new String("Hello"); // string object
const s = Boolean(myString); // initial value of true
```


 
**Warning:** You should rarely find yourself using `Boolean` as a
constructor.




 
### Boolean coercion 

 
Many built-in operations that expect booleans first coerce their
arguments to booleans. [The
operation](https://tc39.es/ecma262/multipage/abstract-operations.html#sec-toboolean)
can be summarized as follows:

-   Booleans are returned as-is.
-   [`undefined`](undefined) turns into `false`.
-   [`null`](../operators/null) turns into `false`.
-   `0`, `-0`, and `NaN` turn into `false`; other numbers turn into
    `true`.
-   `0n` turns into `false`; other [BigInts](bigint) turn into `true`.
-   The empty string `""` turns into `false`; other strings turn into
    `true`.
-   [Symbols](symbol) turn into `true`.
-   All objects become `true`.

 
**Note:** A legacy behavior makes
[`document.all`](https://developer.mozilla.org/en-US/docs/Web/API/Document/all)
return `false` when used as a boolean, despite it being an object. This
property is legacy and non-standard and should not be used.


 
**Note:** Unlike other type conversions like [string
coercion](string#string_coercion) or [number
coercion](number#number_coercion), boolean coercion does not attempt to
convert objects to primitives.


In other words, there are only a handful of values that get coerced to
`false` --- these are called
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) values.
All other values are called
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
values. A value\'s truthiness is important when used with logical
operators, conditional statements, or any boolean context.

There are two ways to achieve the same effect in JavaScript.

-   [Double NOT](../operators/logical_not#double_not_!!): `!!x` negates
    `x` twice, which converts `x` to a boolean using the same algorithm
    as above.
-   The [`Boolean()`](boolean/boolean) function: `Boolean(x)` uses the
    same algorithm as above to convert `x`.

Note that truthiness is not the same as being [loosely
equal](../operators/equality) to `true` or `false`.

 
 
[js]


```js
if ([]) {
  console.log("[] is truthy");
}
if ([] == false) {
  console.log("[] == false");
}
// [] is truthy
// [] == false
```


`[]` is truthy, but it\'s also loosely equal to `false`. It\'s truthy,
because all objects are truthy. However, when comparing with `false`,
which is a primitive, `[]` is also converted to a primitive, which is
`""` via [`Array.prototype.toString()`](array/tostring). Comparing
strings and booleans results in both being [converted to
numbers](number#number_coercion), and they both become `0`, so
`[] == false` is `true`. In general, falsiness and `== false` differ in
the following cases:

-   `NaN`, `undefined`, and `null` are falsy but not loosely equal to
    `false`.
-   `"0"` (and other string literals that are not `""` but [get coerced
    to 0](number#number_coercion)) is truthy but loosely equal to
    `false`.
-   Objects are always truthy, but their primitive representation may be
    loosely equal to `false`.

Truthy values are even more unlikely to be loosely equal to `true`. All
values are either truthy or falsy, but most values are loosely equal to
neither `true` nor `false`.



 
Constructor
-----------

 

[`Boolean()`](boolean/boolean)

:   Creates a new `Boolean` object.



 
Instance properties 
-------------------

 
These properties are defined on `Boolean.prototype` and shared by all
`Boolean` instances.

[`Boolean.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Boolean` instances, the initial value is the
    [`Boolean`](boolean/boolean) constructor.



 
Instance methods 
----------------

 

[`Boolean.prototype.toString()`](boolean/tostring)

:   Returns a string of either `true` or `false` depending upon the
    value of the object. Overrides the
    [`Object.prototype.toString()`](object/tostring) method.

[`Boolean.prototype.valueOf()`](boolean/valueof)

:   Returns the primitive value of the [`Boolean`](boolean) object.
    Overrides the [`Object.prototype.valueOf()`](object/valueof) method.



 
Examples
--------


 
### Creating Boolean objects with an initial value of false 

 
 
 
[js]


```js
const bNoParam = new Boolean();
const bZero = new Boolean(0);
const bNull = new Boolean(null);
const bEmptyString = new Boolean("");
const bfalse = new Boolean(false);
```




 
### Creating Boolean objects with an initial value of true 

 
 
 
[js]


```js
const btrue = new Boolean(true);
const btrueString = new Boolean("true");
const bfalseString = new Boolean("false");
const bSuLin = new Boolean("Su Lin");
const bArrayProto = new Boolean([]);
const bObjProto = new Boolean({});
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-boolean-objects]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-boolean-objects)

  ---------------------------------------------------------------------------------------------------------------


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

`Boolean`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`Boolean`

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

`toString`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`valueOf`

1

12

1

4

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

 
-   [Boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean)
-   [Boolean
    primitives](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#boolean_type)
-   [Boolean data type](https://en.wikipedia.org/wiki/Boolean_data_type)
    on Wikipedia



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean>

