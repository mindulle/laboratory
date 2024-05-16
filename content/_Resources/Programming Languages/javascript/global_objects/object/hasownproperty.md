Object.prototype.hasOwnProperty()
=================================

 
The `hasOwnProperty()` method of [`Object`](../object) instances returns
a boolean indicating whether this object has the specified property as
its own property (as opposed to inheriting it).

 
**Note:** [`Object.hasOwn()`](hasown) is recommended over
`hasOwnProperty()`, in browsers where it is supported.



 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
hasOwnProperty(prop)
```




 
### Parameters

 

[`prop`](#prop)

:   The [`String`](../string) name or [Symbol](../symbol) of the
    property to test.



 
### Return value 

 
Returns `true` if the object has the specified property as own property;
`false` otherwise.



 
Description
-----------

 
The `hasOwnProperty()` method returns `true` if the specified property
is a direct property of the object --- even if the value is `null` or
`undefined`. The method returns `false` if the property is inherited, or
has not been declared at all. Unlike the [`in`](../../operators/in)
operator, this method does not check for the specified property in the
object\'s prototype chain.

The method can be called on *most* JavaScript objects, because most
objects descend from [`Object`](../object), and hence inherit its
methods. For example [`Array`](../array) is an [`Object`](../object), so
you can use `hasOwnProperty()` method to check whether an index exists:

 
 
[js]


```js
const fruits = ["Apple", "Banana", "Watermelon", "Orange"];
fruits.hasOwnProperty(3); // true ('Orange')
fruits.hasOwnProperty(4); // false - not defined
```


The method will not be available in objects where it is reimplemented,
or on [`null`-prototype objects](../object#null-prototype_objects) (as
these don\'t inherit from `Object.prototype`). Examples for these cases
are given below.



 
Examples
--------


 
### Using hasOwnProperty to test for an own property\'s existence 

 
The following code shows how to determine whether the `example` object
contains a property named `prop`.

 
 
[js]


```js
const example = {};
example.hasOwnProperty("prop"); // false

example.prop = "exists";
example.hasOwnProperty("prop"); // true - 'prop' has been defined

example.prop = null;
example.hasOwnProperty("prop"); // true - own property exists with value of null

example.prop = undefined;
example.hasOwnProperty("prop"); // true - own property exists with value of undefined
```




 
### Direct vs. inherited properties 

 
The following example differentiates between direct properties and
properties inherited through the prototype chain:

 
 
[js]


```js
const example = {};
example.prop = "exists";

// `hasOwnProperty` will only return true for direct properties:
example.hasOwnProperty("prop"); // true
example.hasOwnProperty("toString"); // false
example.hasOwnProperty("hasOwnProperty"); // false

// The `in` operator will return true for direct or inherited properties:
"prop" in example; // true
"toString" in example; // true
"hasOwnProperty" in example; // true
```




 
### Iterating over the properties of an object 

 
The following example shows how to iterate over the enumerable
properties of an object without executing on inherited properties.

 
 
[js]


```js
const buz = {
  fog: "stack",
};

for (const name in buz) {
  if (buz.hasOwnProperty(name)) {
    console.log(`this is fog (${name}) for sure. Value: ${buz[name]}`);
  } else {
    console.log(name); // toString or something else
  }
}
```


Note that the [`for...in`](../../statements/for...in) loop only iterates
enumerable items: the absence of non-enumerable properties emitted from
the loop does not imply that `hasOwnProperty` itself is confined
strictly to enumerable items (as with
[`Object.getOwnPropertyNames()`](getownpropertynames)).



 
### Using hasOwnProperty as a property name 

 
JavaScript does not protect the property name `hasOwnProperty`; an
object that has a property with this name may return incorrect results:

 
 
[js]


```js
const foo = {
  hasOwnProperty() {
    return false;
  },
  bar: "Here be dragons",
};

foo.hasOwnProperty("bar"); // re-implementation always returns false
```


The recommended way to overcome this problem is to instead use
[`Object.hasOwn()`](hasown) (in browsers that support it). Other
alternatives include using an *external* `hasOwnProperty`:

 
 
[js]


```js
const foo = { bar: "Here be dragons" };

// Use Object.hasOwn() method - recommended
Object.hasOwn(foo, "bar"); // true

// Use the hasOwnProperty property from the Object prototype
Object.prototype.hasOwnProperty.call(foo, "bar"); // true

// Use another Object's hasOwnProperty
// and call it with 'this' set to foo
({}).hasOwnProperty.call(foo, "bar"); // true
```


Note that in the first two cases there are no newly created objects.



 
### Objects created with Object.create(null) 

 
[`null`-prototype objects](../object#null-prototype_objects) do not
inherit from `Object.prototype`, making `hasOwnProperty()` inaccessible.

 
 
[js]


```js
const foo = Object.create(null);
foo.prop = "exists";
foo.hasOwnProperty("prop"); // Uncaught TypeError: foo.hasOwnProperty is not a function
```


The solutions in this case are the same as for the previous section: use
[`Object.hasOwn()`](hasown) by preference, otherwise use an external
object\'s `hasOwnProperty()`.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.prototype.hasownproperty]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.prototype.hasownproperty)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

`hasOwnProperty`

1

12

1

5

3

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

 
-   [`Object.hasOwn()`](hasown)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [`Object.getOwnPropertyNames()`](getownpropertynames)
-   [`for...in`](../../statements/for...in)
-   [`in`](../../operators/in)
-   [Inheritance and the prototype
    chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty>

