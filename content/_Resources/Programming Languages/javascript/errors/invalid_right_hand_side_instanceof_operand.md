TypeError: invalid \'instanceof\' operand \'x\'
===============================================

 
The JavaScript exception \"invalid \'instanceof\' operand\" occurs when
the right-hand side operands of the [`instanceof`
operator](../operators/instanceof) isn\'t used with a constructor
object, i.e. an object which has a `prototype` property and is callable.


 
Message
-------

 
```text
TypeError: Right-hand side of 'instanceof' is not an object (V8-based)
TypeError: Right-hand side of 'instanceof' is not callable (V8-based)
TypeError: invalid 'instanceof' operand "x" (Firefox)
TypeError: ({}) is not a function (Firefox)
TypeError: Right hand side of instanceof is not an object (Safari)
TypeError: {} is not a function. (evaluating '"x" instanceof {}') (Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror)



 
What went wrong? 
----------------

 
The [`instanceof` operator](../operators/instanceof) expects the
right-hand-side operands to be a constructor object, i.e. an object
which has a `prototype` property and is callable. It can also be an
object with a
[`Symbol.hasInstance`](../global_objects/symbol/hasinstance) method.



 
Examples
--------


 
### instanceof vs. typeof 

 
 
 
[js]


```js
"test" instanceof ""; // TypeError: invalid 'instanceof' operand ""
42 instanceof 0; // TypeError: invalid 'instanceof' operand 0

function Foo() {}
const f = Foo(); // Foo() is called and returns undefined
const x = new Foo();

x instanceof f; // TypeError: invalid 'instanceof' operand f
x instanceof x; // TypeError: x is not a function
```


To fix these errors, you will either need to replace the [`instanceof`
operator](../operators/instanceof) with the [`typeof`
operator](../operators/typeof), or to make sure you use the function
name, instead of the result of its evaluation.

 
 
[js]


```js
typeof "test" === "string"; // true
typeof 42 === "number"; // true

function Foo() {}
const f = Foo; // Do not call Foo.
const x = new Foo();

x instanceof f; // true
x instanceof Foo; // true
```




 
See also 
--------

 
-   [`instanceof`](../operators/instanceof)
-   [`typeof`](../operators/typeof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/invalid_right_hand_side_instanceof_operand>

