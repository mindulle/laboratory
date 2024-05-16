get
===


The `get` syntax binds an object property to a function that will be
called when that property is looked up. It can also be used in
[classes](../classes).



Try it 
------






Syntax
------




[js]


```js
{ get prop() { /* … */ } }
{ get [expression]() { /* … */ } }
```


There are some additional syntax restrictions:

-   A getter must have exactly zero parameters.




### Parameters



[`prop`](#prop)

:   The name of the property to bind to the given function. In the same
    way as other properties in [object
    initializers](../operators/object_initializer), it can be a string
    literal, a number literal, or an identifier.

[`expression`](#expression)

:   You can also use expressions for a computed property name to bind to
    the given function.




Description
-----------


Sometimes it is desirable to allow access to a property that returns a
dynamically computed value, or you may want to reflect the status of an
internal variable without requiring the use of explicit method calls. In
JavaScript, this can be accomplished with the use of a *getter*.

It is not possible to simultaneously have a getter bound to a property
and have that property actually hold a value, although it *is* possible
to use a getter and a setter in conjunction to create a type of
pseudo-property.




Examples
--------



### Defining a getter on new objects in object initializers 


This will create a pseudo-property `latest` for object `obj`, which will
return the last array item in `log`.



[js]


```js
const obj = {
  log: ["example", "test"],
  get latest() {
    if (this.log.length === 0) return undefined;
    return this.log[this.log.length - 1];
  },
};
console.log(obj.latest); // "test"
```


Note that attempting to assign a value to `latest` will not change it.




### Using getters in classes 


You can use the exact same syntax to define public instance getters that
are available on class instances. In classes, you don\'t need the comma
separator between methods.



[js]


```js
class ClassWithGetSet {
  #msg = "hello world";
  get msg() {
    return this.#msg;
  }
  set msg(x) {
    this.#msg = `hello ${x}`;
  }
}

const instance = new ClassWithGetSet();
console.log(instance.msg); // "hello world"

instance.msg = "cake";
console.log(instance.msg); // "hello cake"
```


Getter properties are defined on the `prototype` property of the class
and are thus shared by all instances of the class. Unlike getter
properties in object literals, getter properties in classes are not
enumerable.

Static getters and private getters use similar syntaxes, which are
described in the [`static`](../classes/static) and [](privateProperties.md) pages.




### Deleting a getter using the `delete` operator 


If you want to remove the getter, you can just
[`delete`](../operators/delete) it:



[js]


```js
delete obj.latest;
```





### Defining a getter on existing objects using `defineProperty` 


To append a getter to an existing object later at any time, use
[`Object.defineProperty()`](../global_objects/object/defineproperty).



[js]


```js
const o = { a: 0 };

Object.defineProperty(o, "b", {
  get() {
    return this.a + 1;
  },
});

console.log(o.b); // Runs the getter, which yields a + 1 (which is 1)
```





### Using a computed property name 




[js]


```js
const expr = "foo";

const obj = {
  get [expr]() {
    return "bar";
  },
};

console.log(obj.foo); // "bar"
```





### Defining static getters 




[js]


```js
class MyConstants {
  static get foo() {
    return "foo";
  }
}

console.log(MyConstants.foo); // 'foo'
MyConstants.foo = "bar";
console.log(MyConstants.foo); // 'foo', a static getter's value cannot be changed
```





### Smart / self-overwriting / lazy getters 


Getters give you a way to *define* a property of an object, but they do
not *calculate* the property\'s value until it is accessed. A getter
defers the cost of calculating the value until the value is needed. If
it is never needed, you never pay the cost.

An additional optimization technique to lazify or delay the calculation
of a property value and cache it for later access are *smart* (or
*[memoized](https://en.wikipedia.org/wiki/Memoization)*) getters. The
value is calculated the first time the getter is called, and is then
cached so subsequent accesses return the cached value without
recalculating it. This is useful in the following situations:

-   If the calculation of a property value is expensive (takes much RAM
    or CPU time, spawns worker threads, retrieves remote file, etc.).
-   If the value isn\'t needed just now. It will be used later, or in
    some case it\'s not used at all.
-   If it\'s used, it will be accessed several times, and there is no
    need to re-calculate that value will never be changed or shouldn\'t
    be re-calculated.

 
**Note:** This means that you shouldn\'t write a lazy getter for a
property whose value you expect to change, because if the getter is lazy
then it will not recalculate the value.

Note that getters are not \"lazy\" or \"memoized\" by nature; you must
implement this technique if you desire this behavior.


In the following example, the object has a getter as its own property.
On getting the property, the property is removed from the object and
re-added, but implicitly as a data property this time. Finally, the
value gets returned.



[js]


```js
const obj = {
  get notifier() {
    delete this.notifier;
    this.notifier = document.getElementById("bookmarked-notification-anchor");
    return this.notifier;
  },
};
```





### get vs. defineProperty 


While using the `get` keyword and
[`Object.defineProperty()`](../global_objects/object/defineproperty)
have similar results, there is a subtle difference between the two when
used on [`classes`](../classes).

When using `get` the property will be defined on the instance\'s
prototype, while using
[`Object.defineProperty()`](../global_objects/object/defineproperty) the
property will be defined on the instance it is applied to.



[js]


```js
class Example {
  get hello() {
    return "world";
  }
}

const obj = new Example();
console.log(obj.hello);
// "world"

console.log(Object.getOwnPropertyDescriptor(obj, "hello"));
// undefined

console.log(
  Object.getOwnPropertyDescriptor(Object.getPrototypeOf(obj), "hello"),
);
// { configurable: true, enumerable: false, get: function get hello() { return 'world'; }, set: undefined }
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-method-definitions]](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#sec-method-definitions)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`get`

1

12

1.5

9.5

3

18

4

14

1

1.0

4.4

1.0

0.10.0

`computed_property_names`

46

12

34

47

9.1

46

34

33

9.3

5.0

46

1.0

4.0.0


See also 
--------


-   [Working with
    objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects)
    guide
-   [Functions](../functions)
-   [`set`](set)
-   [`Object.defineProperty()`](../global_objects/object/defineproperty)
-   [Object initializer](../operators/object_initializer)
-   [`class`](../statements/class)
-   [Property accessors](../operators/property_accessors)
-   [Incompatible ES5 change: literal getter and setter functions must
    now have exactly zero or one
    arguments](https://whereswalden.com/2010/08/22/incompatible-es5-change-literal-getter-and-setter-functions-must-now-have-exactly-zero-or-one-arguments/)
    by Jeff Walden (2010)
-   [More SpiderMonkey changes: ancient, esoteric, very rarely used
    syntax for creating getters and setters is being
    removed](https://whereswalden.com/2010/04/16/more-spidermonkey-changes-ancient-esoteric-very-rarely-used-syntax-for-creating-getters-and-setters-is-being-removed/)
    by Jeff Walden (2010)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get>

