with
====

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Note:** Use of the `with` statement is not recommended, as it may be
the source of confusing bugs and compatibility issues, makes
optimization impossible, and is forbidden in [strict
mode](../strict_mode). The recommended alternative is to assign the
object whose properties you want to access to a temporary variable.


The `with` statement extends the scope chain for a statement.


 
Syntax
------

 
 
 
[js]


```js
with (expression)
  statement
```


[`expression`](#expression)

:   Adds the given expression to the scope chain used when evaluating
    the statement. The parentheses around the expression are required.

[`statement`](#statement)

:   Any statement. To execute multiple statements, use a [block](block)
    statement (`{ ... }`) to group those statements.



 
Description
-----------

 
There are two types of identifiers: a *qualified* identifier and an
*unqualified* identifier. An unqualified identifier is one that does not
indicate where it comes from.

 
 
[js]


```js
foo; // unqualified identifier
foo.bar; // bar is a qualified identifier
```


Normally, an unqualified identifier is resolved by searching the scope
chain for a variable with that name, while a qualified identifier is
resolved by searching the prototype chain of an object for a property
with that name.

 
 
[js]


```js
const foo = { bar: 1 };
console.log(foo.bar);
// foo is found in the scope chain as a variable;
// bar is found in foo as a property
```


One exception to this is the [global
object](https://developer.mozilla.org/en-US/docs/Glossary/Global_object),
which sits on top of the scope chain, and whose properties automatically
become global variables that can be referred to without qualifiers.

 
 
[js]


```js
console.log(globalThis.Math === Math); // true
```


The `with` statement adds the given object to the head of this scope
chain during the evaluation of its statement body. Every unqualified
name would first be searched within the object (through a
[`in`](../operators/in) check) before searching in the upper scope
chain.

Note that if the unqualified reference refers to a method of the object,
the method is called with the object as its `this` value.

 
 
[js]


```js
with ([1, 2, 3]) {
  console.log(toString()); // 1,2,3
}
```


The object may have an
[`@@unscopables`](../global_objects/symbol/unscopables) property, which
defines a list of properties that should not be added to the scope chain
(for backward compatibility). See the
[`Symbol.unscopables`](../global_objects/symbol/unscopables)
documentation for more information.

The reasons to use a `with` statement include saving one temporary
variable and reducing file size by avoiding repeating a lengthy object
reference. However, there are far more reasons why `with` statements are
not desirable:

-   Performance: The `with` statement forces the specified object to be
    searched first for all name lookups. Therefore, all identifiers that
    aren\'t members of the specified object will be found more slowly in
    a `with` block. Moreover, the optimizer cannot make any assumptions
    about what each unqualified identifier refers to, so it must repeat
    the same property lookup every time the identifier is used.
-   Readability: The `with` statement makes it hard for a human reader
    or JavaScript compiler to decide whether an unqualified name will be
    found along the scope chain, and if so, in which object. For
    example:
     
     
    [js]
    

    ```js
    function f(x, o) {
      with (o) {
        console.log(x);
      }
    }
    ```
    

    If you look just at the definition of `f`, it\'s impossible to tell
    what the `x` in the `with` body refers to. Only when `f` is called
    can `x` be determined to be `o.x` or `f`\'s first formal parameter.
    If you forget to define `x` in the object you pass as the second
    parameter, you won\'t get an error --- instead you\'ll just get
    unexpected results. It\'s also unclear what the actual intent of
    such code would be.
-   Forward compatibility: Code using `with` may not be forward
    compatible, especially when used with something other than a plain
    object, which may gain more properties in the future. Consider this
    example:
     
     
    [js]
    

    ```js
    function f(foo, values) {
      with (foo) {
        console.log(values);
      }
    }
    ```
    

    If you call `f([1, 2, 3], obj)` in an ECMAScript 5 environment, the
    `values` reference inside the `with` statement will resolve to
    `obj`. However, ECMAScript 2015 introduces a
    [`values`](../global_objects/array/values) property on
    `Array.prototype` (so it will be available on every array). So,
    after upgrading the environment, the `values` reference inside the
    `with` statement resolves to `[1, 2, 3].values` instead, and is
    likely to cause bugs. In this particular example, `values` is
    defined as unscopable through
    [`Array.prototype[@@unscopables]`](../global_objects/array/@@unscopables),
    so it still correctly resolves to the `values` parameter. If it were
    not defined as unscopable, one can see how this would be a difficult
    issue to debug.



 
Examples
--------


 
### Using the with statement 

 
The following `with` statement specifies that the
[`Math`](../global_objects/math) object is the default object. The
statements following the `with` statement refer to the
[`PI`](../global_objects/math/pi) property and the
[`cos`](../global_objects/math/cos) and
[`sin`](../global_objects/math/sin) methods, without specifying an
object. JavaScript assumes the `Math` object for these references.

 
 
[js]


```js
let a, x, y;
const r = 10;

with (Math) {
  a = PI * r * r;
  x = r * cos(PI);
  y = r * sin(PI / 2);
}
```




 
### Avoiding the with statement by destructuring properties into the current scope 

 
You can usually avoid using `with` through [property
destructuring](../operators/destructuring_assignment). Here we create an
extra block to mimic the behavior of `with` creating an extra scope ---
but in actual usage, this block can usually be omitted.

 
 
[js]


```js
let a, x, y;
const r = 10;

{
  const { PI, cos, sin } = Math;
  a = PI * r * r;
  x = r * cos(PI);
  y = r * sin(PI / 2);
}
```




 
### Avoiding the with statement by using an IIFE 

 
If you\'re producing an expression that must reuse a long-named
reference multiple times, and your goal is to eliminate that lengthy
name within your expression, you can wrap the expression in an
[IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) and
provide the long name as an argument.

 
 
[js]


```js
const objectHavingAnEspeciallyLengthyName = { foo: true, bar: false };

if (((o) => o.foo && !o.bar)(objectHavingAnEspeciallyLengthyName)) {
  // This branch runs.
}
```




 
### Creating dynamic namespaces using the with statement and a proxy 

 
`with` will transform every variable lookup to a property lookup, while
[Proxies](../global_objects/proxy) allow trapping every property lookup
call. You can create a dynamic namespace by combining them.

 
 
[js]


```js
const namespace = new Proxy(
  {},
  {
    has(target, key) {
      // Avoid trapping global properties like `console`
      if (key in globalThis) {
        return false;
      }
      // Trap all property lookups
      return true;
    },
    get(target, key) {
      return key;
    },
  },
);

with (namespace) {
  console.log(a, b, c); // "a" "b" "c"
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-with-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-with-statement)

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

`with`

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

 
-   [block](block)
-   [Strict mode](../strict_mode)
-   [`Symbol.unscopables`](../global_objects/symbol/unscopables)
-   [`Array.prototype[@@unscopables]`](../global_objects/array/@@unscopables)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/with>

