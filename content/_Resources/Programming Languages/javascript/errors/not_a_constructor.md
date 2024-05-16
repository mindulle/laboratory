TypeError: \"x\" is not a constructor
=====================================

 
The JavaScript exception \"is not a constructor\" occurs when there was
an attempt to use an object or a variable as a constructor, but that
object or variable is not a constructor.


 
Message
-------

 
```text
TypeError: x is not a constructor (V8-based & Firefox & Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror)



 
What went wrong? 
----------------

 
There was an attempt to use an object or a variable as a constructor,
but that object or variable is not a constructor. See
[constructor](https://developer.mozilla.org/en-US/docs/Glossary/Constructor)
or the [`new` operator](../operators/new) for more information on what a
constructor is.

There are many global objects, like [`String`](../global_objects/string)
or [`Array`](../global_objects/array), which are constructable using
`new`. However, some global objects are not and their properties and
methods are static. The following JavaScript standard built-in objects
are not a constructor: [`Math`](../global_objects/math),
[`JSON`](../global_objects/json), [`Symbol`](../global_objects/symbol),
[`Reflect`](../global_objects/reflect),
[`Intl`](../global_objects/intl),
[`Atomics`](../global_objects/atomics).

[Generator functions](../statements/function*) cannot be used as
constructors either.



 
Examples
--------


 
### Invalid cases 

 
 
 
[js]


```js
const Car = 1;
new Car();
// TypeError: Car is not a constructor

new Math();
// TypeError: Math is not a constructor

new Symbol();
// TypeError: Symbol is not a constructor

function* f() {}
const obj = new f();
// TypeError: f is not a constructor
```




 
### A car constructor 

 
Suppose you want to create an object type for cars. You want this type
of object to be called `Car`, and you want it to have properties for
make, model, and year. To do this, you would write the following
function:

 
 
[js]


```js
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}
```


Now you can create an object called `mycar` as follows:

 
 
[js]


```js
const mycar = new Car("Eagle", "Talon TSi", 1993);
```




 
### In Promises 

 
When returning an immediately-resolved or immediately-rejected Promise,
you do not need to create a `new Promise(...)` and act on it. Instead,
use the [`Promise.resolve()`](../global_objects/promise/resolve) or
[`Promise.reject()`](../global_objects/promise/reject) [static
methods](https://en.wikipedia.org/wiki/Method_(computer_programming)#Static_methods).

This is not legal (the [`Promise`
constructor](../global_objects/promise/promise) is not being called
correctly) and will throw a `TypeError: this is not a constructor`
exception:

 
 
[js]


```js
const fn = () => {
  return new Promise.resolve(true);
};
```


This is legal, but unnecessarily long:

 
 
[js]


```js
const fn = () => {
  return new Promise((resolve, reject) => {
    resolve(true);
  });
};
```


Instead, return the static method:

 
 
[js]


```js
const resolveAlways = () => {
  return Promise.resolve(true);
};

const rejectAlways = () => {
  return Promise.reject(false);
};
```




 
See also 
--------

 
-   [constructor](https://developer.mozilla.org/en-US/docs/Glossary/Constructor)
-   [`new`](../operators/new)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_constructor>

