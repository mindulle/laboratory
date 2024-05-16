SyntaxError: invalid assignment left-hand side
==============================================

 
The JavaScript exception \"invalid assignment left-hand side\" occurs
when there was an unexpected assignment somewhere. It may be triggered
when a single `=` sign was used instead of `==` or `===`.


 
Message
-------

 
```text
SyntaxError: Invalid left-hand side in assignment (V8-based)
SyntaxError: invalid assignment left-hand side (Firefox)
SyntaxError: Left side of assignment is not a reference. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror) or
[`ReferenceError`](../global_objects/referenceerror), depending on the
syntax.



 
What went wrong? 
----------------

 
There was an unexpected assignment somewhere. This might be due to a
mismatch of an [assignment
operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#assignment_operators)
and an [equality
operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#equality_operators),
for example. While a single `=` sign assigns a value to a variable, the
`==` or `===` operators compare a value.



 
Examples
--------


 
### Typical invalid assignments 

 
 
 
[js]


```js
if (Math.PI + 1 = 3 || Math.PI + 1 = 4) {
  console.log("no way!");
}
// SyntaxError: invalid assignment left-hand side

const str = "Hello, "
+= "is it me "
+= "you're looking for?";
// SyntaxError: invalid assignment left-hand side
```


In the `if` statement, you want to use an equality operator (`===`), and
for the string concatenation, the plus (`+`) operator is needed.

 
 
[js]


```js
if (Math.PI + 1 === 3 || Math.PI + 1 === 4) {
  console.log("no way!");
}

const str = "Hello, "
  + "from the "
  + "other side!";
```




 
### Assignments producing ReferenceErrors 

 
Invalid assignments don\'t always produce syntax errors. Sometimes the
syntax is almost correct, but at runtime, the left hand side expression
evaluates to a *value* instead of a *reference*, so the assignment is
still invalid. Such errors occur later in execution, when the statement
is actually executed.

 
 
[js]


```js
function foo() {
  return { a: 1 };
}
foo() = 1; // ReferenceError: invalid assignment left-hand side
```


Function calls, [`new`](../operators/new) calls,
[`super()`](../operators/super), and [`this`](../operators/this) are all
values instead of references. If you want to use them on the left hand
side, the assignment target needs to be a property of their produced
values instead.

 
 
[js]


```js
function foo() {
  return { a: 1 };
}
foo().a = 1;
```


 
**Note:** In Firefox and Safari, the first example produces a
`ReferenceError` in non-strict mode, and a `SyntaxError` in [strict
mode](../strict_mode). Chrome throws a runtime `ReferenceError` for both
strict and non-strict modes.




 
### Using optional chaining as assignment target 

 
[Optional chaining](../operators/optional_chaining) is not a valid
target of assignment.

 
 
[js]


```js
obj?.foo = 1; // SyntaxError: invalid assignment left-hand side
```


Instead, you have to first guard the nullish case.

 
 
[js]


```js
if (obj) {
  obj.foo = 1;
}
```




 
See also 
--------

 
-   [Assignment
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#assignment_operators)
-   [Equality
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#equality_operators)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_assignment_left-hand_side>

