Symbol.hasInstance
==================

 
The `Symbol.hasInstance` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@hasInstance`. The
[`instanceof`](../../operators/instanceof) operator looks up this symbol
on its right-hand operand for the method used to determine if the
constructor object recognizes an object as its instance.


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@hasInstance`.

 
Property attributes of `Symbol.hasInstance`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
The `instanceof` operator uses the following algorithm to calculate the
return value of `object instanceof constructor`:

1.  If `constructor` has a `@@hasInstance` method, then call it with
    `object` as the first argument and return the result, [coerced to a
    boolean](../boolean#boolean_coercion). Throw a
    [`TypeError`](../typeerror) if `constructor` is not an object, or if
    `constructor[@@hasInstance]` is not one of `null`, `undefined`, or a
    function.
2.  Otherwise, if `constructor` doesn\'t have a `@@hasInstance` method
    (`constructor[@@hasInstance]` is `null` or `undefined`), then
    determine the result using the same algorithm as
    [`Function.prototype[@@hasInstance]`](../function/@@hasinstance).
    Throw a [`TypeError`](../typeerror) if `constructor` is not a
    function.

Because all functions inherit from `Function.prototype` by default, most
of the time, the
[`Function.prototype[@@hasInstance]`](../function/@@hasinstance) method
specifies the behavior of `instanceof` when the right-hand side is a
function.



 
Examples
--------


 
### Custom instanceof behavior 

 
You could implement your custom `instanceof` behavior like this, for
example:

 
 
[js]


```js
class MyArray {
  static [Symbol.hasInstance](instance) {
    return Array.isArray(instance);
  }
}
console.log([] instanceof MyArray); // true
```


 
 
[js]


```js
function MyArray() {}
Object.defineProperty(MyArray, Symbol.hasInstance, {
  value(instance) {
    return Array.isArray(instance);
  },
});
console.log([] instanceof MyArray); // true
```




 
### Checking the instance of an object 

 
Just in the same manner at which you can check if an object is an
instance of a class using the `instanceof` keyword, we can also use
`Symbol.hasInstance` for such checks.

 
 
[js]


```js
class Animal {
  constructor() {}
}

const cat = new Animal();

console.log(Animal[Symbol.hasInstance](cat)); // true
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.hasinstance]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.hasinstance)

  ---------------------------------------------------------------------------------------------------------------------


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

`hasInstance`

50

15

50

37

10

50

50

37

10

5.0

50

1.0

6.5.0

 
See also 
--------

 
-   [`instanceof`](../../operators/instanceof)
-   [`Function.prototype[@@hasInstance]()`](../function/@@hasinstance)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/hasInstance>

