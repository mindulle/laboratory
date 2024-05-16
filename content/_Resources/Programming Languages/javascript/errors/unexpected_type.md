TypeError: \"x\" is (not) \"y\"
===============================

 
The JavaScript exception \"*x* is (not) *y*\" occurs when there was an
unexpected type. Oftentimes, unexpected
[`undefined`](../global_objects/undefined) or
[`null`](../operators/null) values.


 
Message
-------

 
```text
TypeError: Cannot read properties of undefined (reading 'x') (V8-based)
TypeError: "x" is undefined (Firefox)
TypeError: "undefined" is not an object (Firefox)
TypeError: undefined is not an object (evaluating 'obj.x') (Safari)

TypeError: "x" is not a symbol (V8-based & Firefox)
TypeError: Symbol.keyFor requires that the first argument be a symbol (Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror).



 
What went wrong? 
----------------

 
There was an unexpected type. This occurs oftentimes with
[`undefined`](../global_objects/undefined) or
[`null`](../operators/null) values.

Also, certain methods, such as
[`Object.create()`](../global_objects/object/create) or
[`Symbol.keyFor()`](../global_objects/symbol/keyfor), require a specific
type, that must be provided.



 
Examples
--------


 
### Invalid cases 

 
You cannot invoke a method on an `undefined` or `null` variable.

 
 
[js]


```js
const foo = undefined;
foo.substring(1); // TypeError: foo is undefined

const foo2 = null;
foo2.substring(1); // TypeError: foo is null
```


Certain methods might require a specific type.

 
 
[js]


```js
const foo = {};
Symbol.keyFor(foo); // TypeError: foo is not a symbol

const foo2 = "bar";
Object.create(foo2); // TypeError: "foo" is not an object or null
```




 
### Fixing the issue 

 
To fix null pointer to `undefined` or `null` values, you can test if the
value is `undefined` or `null` first.

 
 
[js]


```js
if (foo !== undefined && foo !== null) {
  // Now we know that foo is defined, we are good to go.
}
```


Or, if you are confident that `foo` will not be another
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value
like `""` or `0`, or if filtering those cases out is not an issue, you
can simply test for its truthiness.

 
 
[js]


```js
if (foo) {
  // Now we know that foo is truthy, it will necessarily not be null/undefined.
}
```




 
See also 
--------

 
-   [`undefined`](../global_objects/undefined)
-   [`null`](../operators/null)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unexpected_type>

