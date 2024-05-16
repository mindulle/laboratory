Function.prototype\[@\@hasInstance\]()
======================================

 
The `[@@hasInstance]()` method of [`Function`](../function) instances
specifies the default procedure for determining if a constructor
function recognizes an object as one of the constructor\'s instances. It
is called by the [`instanceof`](../../operators/instanceof) operator.


 
Syntax
------

 
 
 
[js]


```js
func[Symbol.hasInstance](value)
```




 
### Parameters

 

[`value`](#value)

:   The object to test. Primitive values always return `false`.



 
### Return value 

 
`true` if `func.prototype` is in the prototype chain of `value`;
otherwise, `false`. Always returns `false` if `value` is not an object
or `this` is not a function. If `this` is a [bound function](bind),
returns the result of a `instanceof` test on `value` and the underlying
target function.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `this` is not a bound function and `this.prototype` is not
    an object.



 
Description
-----------

 
The [`instanceof`](../../operators/instanceof) operator calls the
[`[@@hasInstance]()`](../symbol/hasinstance) method of the right-hand
side whenever such a method exists. Because all functions inherit from
`Function.prototype` by default, they would all have the
`[@@hasInstance]()` method, so most of the time, the
`Function.prototype[@@hasInstance]` method specifies the behavior of
`instanceof` when the right-hand side is a function. This method
implements the default behavior of the `instanceof` operator (the same
algorithm when `constructor` has no `@@hasInstance` method).

Unlike most methods, the `Function.prototype[@@hasInstance]()` property
is non-configurable and non-writable. This is a security feature to
prevent the underlying target function of a bound function from being
obtainable. See [this StackOverflow
answer](https://stackoverflow.com/questions/38215027/trying-to-understand-the-official-es6-spec-regarding-symbol-hasinstance/38215392#38215392)
for an example.



 
Examples
--------


 
### Reverting to default instanceof behavior 

 
You would rarely need to call this method directly. Instead, this method
is called by the `instanceof` operator. You should expect the two
results to usually be equivalent.

 
 
[js]


```js
class Foo {}
const foo = new Foo();
console.log(foo instanceof Foo === Foo[Symbol.hasInstance](foo)); // true
```


You may want to use this method if you want to invoke the default
`instanceof` behavior, but you don\'t know if a constructor has a
overridden `[@@hasInstance]()` method.

 
 
[js]


```js
class Foo {
  static [Symbol.hasInstance](value) {
    // A custom implementation
    return false;
  }
}

const foo = new Foo();
console.log(foo instanceof Foo); // false
console.log(Function.prototype[Symbol.hasInstance].call(Foo, foo)); // true
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function.prototype-@\@hasinstance]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function.prototype-@@hasinstance)

  --------------------------------------------------------------------------------------------------------------------------------------------------


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

`@@hasInstance`

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
-   [`Symbol.hasInstance`](../symbol/hasinstance)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/@@hasInstance>

