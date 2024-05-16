Method definitions
==================


**Method definition** is a shorter syntax for defining a function
property in an object initializer. It can also be used in
[classes](../classes).



Try it 
------






Syntax
------




[js]


```js
({
  property(parameters) {},
  *generator(parameters) {},
  async property(parameters) {},
  async *generator(parameters) {},

  // with computed keys
  [expression](parameters) {},
  *[expression](parameters) {},
  async [expression](parameters) {},
  async *[expression](parameters) {},
})
```





Description
-----------


The shorthand syntax is similar to the [getter](get) and [setter](set)
syntax.

Given the following code:



[js]


```js
const obj = {
  foo: function () {
    // …
  },
  bar: function () {
    // …
  },
};
```


You are now able to shorten this to:



[js]


```js
const obj = {
  foo() {
    // …
  },
  bar() {
    // …
  },
};
```


[`function*`](../statements/function*),
[`async function`](../statements/async_function), and
[`async function*`](../statements/async_function*) properties all have
their respective method syntaxes; see examples below.

However, note that the method syntax is not equivalent to a normal
property with a function as its value --- there are semantic
differences. This makes methods defined in object literals more
consistent with methods in [classes](../classes).




### Method definitions are not constructable 


Methods cannot be constructors! They will throw a
[`TypeError`](../global_objects/typeerror) if you try to instantiate
them. On the other hand, a property created as a function can be used as
a constructor.



[js]


```js
const obj = {
  method() {},
};
new obj.method(); // TypeError: obj.method is not a constructor
```





### Using super in method definitions 


Only functions defined as methods have access to the
[`super`](../operators/super) keyword. `super.prop` looks up the
property on the prototype of the object that the method was initialized
on.



[js]


```js
const obj = {
  __proto__: {
    prop: "foo",
  },
  notAMethod: function () {
    console.log(super.prop); // SyntaxError: 'super' keyword unexpected here
  },
};
```





Examples
--------



### Using method definitions 




[js]


```js
const obj = {
  a: "foo",
  b() {
    return this.a;
  },
};
console.log(obj.b()); // "foo"
```





### Method definitions in classes 


You can use the exact same syntax to define public instance methods that
are available on class instances. In classes, you don\'t need the comma
separator between methods.



[js]


```js
class ClassWithPublicInstanceMethod {
  publicMethod() {
    return "hello world";
  }
  secondPublicMethod() {
    return "goodbye world";
  }
}

const instance = new ClassWithPublicInstanceMethod();
console.log(instance.publicMethod()); // "hello world"
```


Public instance methods are defined on the `prototype` property of the
class and are thus shared by all instances of the class. They are
writable, non-enumerable, and configurable.

Inside instance methods, [`this`](../operators/this) and
[`super`](../operators/super) work like in normal methods. Usually,
`this` refers to the instance itself. In subclasses, `super` lets you
access the prototype of the object that the method is attached to,
allowing you to call methods from the superclass.



[js]


```js
class BaseClass {
  msg = "hello world";
  basePublicMethod() {
    return this.msg;
  }
}

class SubClass extends BaseClass {
  subPublicMethod() {
    return super.basePublicMethod();
  }
}

const instance = new SubClass();
console.log(instance.subPublicMethod()); // "hello world"
```


Static methods and private methods use similar syntaxes, which are
described in the [`static`](../classes/static) and [](privateProperties.md) pages.




### Computed property names 


The method syntax also supports [computed property
names](../operators/object_initializer#computed_property_names).



[js]


```js
const bar = {
  foo0: function () {
    return 0;
  },
  foo1() {
    return 1;
  },
  ["foo" + 2]() {
    return 2;
  },
};

console.log(bar.foo0()); // 0
console.log(bar.foo1()); // 1
console.log(bar.foo2()); // 2
```





### Generator methods 


Note that the asterisk (`*`) in the generator method syntax must be
*before* the generator property name. (That is, `* g(){}` will work, but
`g *(){}` will not.)



[js]


```js
// Using a named property
const obj = {
  g: function* () {
    let index = 0;
    while (true) {
      yield index++;
    }
  },
};

// The same object using shorthand syntax
const obj2 = {
  *g() {
    let index = 0;
    while (true) {
      yield index++;
    }
  },
};

const it = obj2.g();
console.log(it.next().value); // 0
console.log(it.next().value); // 1
```





### Async methods 




[js]


```js
// Using a named property
const obj = {
  f: async function () {
    await somePromise;
  },
};

// The same object using shorthand syntax
const obj2 = {
  async f() {
    await somePromise;
  },
};
```





### Async generator methods 




[js]


```js
const obj = {
  f: async function* () {
    yield 1;
    yield 2;
    yield 3;
  },
};

// The same object using shorthand syntax
const obj2 = {
  async *f() {
    yield 1;
    yield 2;
    yield 3;
  },
};
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

`Method_definitions`

39

12

34

26

9

39

34

26

9

4.0

39

1.0

4.0.0

`async_generator_methods`

63

79

55

50

12

63

55

46

12

8.0

63

1.0

10.0.0

`async_methods`

55

15

52

42

10.1

55

52

42

10.3

6.0

55

1.0

7.6.0

`generator_methods_not_constructable`

42

13

43

29

9.1

42

43

29

9.3

4.0

42

1.0

6.0.0


See also 
--------


-   [Working with
    objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects)
    guide
-   [Functions](../functions)
-   [`get`](get)
-   [`set`](set)
-   [Object initializer](../operators/object_initializer)
-   [`class`](../statements/class)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions>

