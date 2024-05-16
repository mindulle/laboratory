Function.prototype.toString()
=============================

 
The `toString()` method of [`Function`](../function) instances returns a
string representing the source code of this function.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the source code of the function.



 
Description
-----------

 
The [`Function`](../function) object overrides the `toString()` method
inherited from [`Object`](../object); it does not inherit
[`Object.prototype.toString`](../object/tostring). For user-defined
`Function` objects, the `toString` method returns a string containing
the source text segment which was used to define the function.

JavaScript calls the `toString` method automatically when a `Function`
is to be represented as a text value, e.g. when a function is
concatenated with a string.

The `toString()` method will throw a [`TypeError`](../typeerror)
exception (\"Function.prototype.toString called on incompatible
object\"), if its `this` value object is not a `Function` object.

 
 
[js]


```js
Function.prototype.toString.call("foo"); // throws TypeError
```


If the `toString()` method is called on built-in function objects, a
function created by [`Function.prototype.bind()`](bind), or other
non-JavaScript functions, then `toString()` returns a *native function
string* which looks like

```text
function someName() { [native code] }
```

For intrinsic object methods and functions, `someName` is the initial
name of the function; otherwise its content may be
implementation-defined, but will always be in property name syntax, like
`[1 + 1]`, `someName`, or `1`.

 
**Note:** This means using [`eval()`](../eval) on native function
strings is a guaranteed syntax error.


If the `toString()` method is called on a function created by the
`Function` constructor, `toString()` returns the source code of a
synthesized function declaration named \"anonymous\" using the provided
parameters and function body. For example,
`Function("a", "b", "return a + b").toString()` will return:

```text
function anonymous(a,b
) {
return a + b
}
```

Since ES2018, the spec requires the return value of `toString()` to be
the exact same source code as it was declared, including any whitespace
and/or comments --- or, if the host doesn\'t have the source code
available for some reason, requires returning a native function string.
Support for this revised behavior can be found in the [compatibility
table](#browser_compatibility).



 
Examples
--------


 
### Comparing actual source code and toString results 

 
 
 
[js]


```js
function test(fn) {
  console.log(fn.toString());
}

function f() {}
class A {
  a() {}
}
function* g() {}

test(f); // "function f() {}"
test(A); // "class A { a() {} }"
test(g); // "function* g() {}"
test((a) => a); // "(a) => a"
test({ a() {} }.a); // "a() {}"
test({ *a() {} }.a); // "*a() {}"
test({ [0]() {} }[0]); // "[0]() {}"
test(Object.getOwnPropertyDescriptor({ get a() {} }, "a").get); // "get a() {}"
test(Object.getOwnPropertyDescriptor({ set a(x) {} }, "a").set); // "set a(x) {}"
test(Function.prototype.toString); // "function toString() { [native code] }"
test(function f() {}.bind(0)); // "function () { [native code] }"
test(Function("a", "b")); // function anonymous(a\n) {\nb\n}
```


Note that after the `Function.prototype.toString()` revision, when
`toString()` is called, implementations are never allowed to synthesize
a function\'s source that is not a native function string. The method
always returns the exact source code used to create the function ---
including the [getter](../../functions/get) and
[setter](../../functions/set) examples above. The
[`Function`](../../functions) constructor itself has the capability of
synthesizing the source code for the function (and is therefore a form
of implicit [`eval()`](../eval)).



 
### Getting source text of a function 

 
It is possible to get the source text of a function by coercing it to a
string --- for example, by wrapping it in a template literal:

 
 
[js]


```js
function foo() {
  return "bar";
}
console.log(`${foo}`);
// function foo() {
//   return "bar";
// }
```


This source text is *exact*, including any interspersed comments (which
won\'t be stored by the engine\'s internal representation otherwise).

 
 
[js]


```js
function foo /* a comment */() {
  return "bar";
}
console.log(foo.toString());
// function foo /* a comment */() {
//   return "bar";
// }
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function.prototype.tostring]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function.prototype.tostring)

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

`toString`

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

`toString_revision`

66

79

54

53

No

66

54

47

No

9.0

66

1.0

No

 
See also 
--------

 
-   [`Object.prototype.toString()`](../object/tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/toString>

