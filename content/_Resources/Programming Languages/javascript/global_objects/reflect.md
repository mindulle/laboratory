Reflect
=======

 
The `Reflect` namespace object contains static methods for invoking
interceptable JavaScript object internal methods. The methods are the
same as those of [proxy handlers](proxy/proxy).


 
Description
-----------

 
Unlike most global objects, `Reflect` is not a constructor. You cannot
use it with the [`new` operator](../operators/new) or invoke the
`Reflect` object as a function. All properties and methods of `Reflect`
are static (just like the [`Math`](math) object).

The `Reflect` object provides a collection of static functions which
have the same names as the [proxy handler methods](proxy/proxy).

The major use case of `Reflect` is to provide default forwarding
behavior in `Proxy` handler traps. A [trap](proxy#terminology) is used
to intercept an operation on an object --- it provides a custom
implementation for an [object internal
method](proxy#object_internal_methods). The `Reflect` API is used to
invoke the corresponding internal method. For example, the code below
creates a proxy `p` with a
[`deleteProperty`](proxy/proxy/deleteproperty) trap that intercepts the
`[[Delete]]` internal method. `Reflect.deleteProperty()` is used to
invoke the default `[[Delete]]` behavior on `targetObject` directly. You
can replace it with [`delete`](../operators/delete), but using `Reflect`
saves you from having to remember the syntax that each internal method
corresponds to.

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    deleteProperty(targetObject, property) {
      // Custom functionality: log the deletion
      console.log("Deleting property:", property);

      // Execute the default introspection behavior
      return Reflect.deleteProperty(targetObject, property);
    },
  },
);
```


The `Reflect` methods also allow finer control of how the internal
method is invoked. For example,
[`Reflect.construct()`](reflect/construct) is the only way to construct
a target function with a specific
[`new.target`](../operators/new.target) value. If you use the
[`new`](../operators/new) operator to invoke a function, the
`new.target` value is always the function itself. This has important
effects with
[subclassing](../operators/new.target#new.target_using_reflect.construct).
For another example, [`Reflect.get()`](reflect/get) allows you to run a
[getter](../functions/get) with a custom `this` value, while [property
accessors](../operators/property_accessors) always use the current
object as the `this` value.

Nearly every `Reflect` method\'s behavior can be done with some other
syntax or method. Some of these methods have corresponding static
methods of the same name on [`Object`](object), although they do have
some subtle differences. For the exact differences, see the description
for each `Reflect` method.



 
Static properties 
-----------------

 

[`Reflect[@@toStringTag]`](#reflecttostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Reflect"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Static methods 
--------------

 

[`Reflect.apply()`](reflect/apply)

:   Calls a `target` function with arguments as specified by the
    `argumentsList` parameter. See also
    [`Function.prototype.apply()`](function/apply).

[`Reflect.construct()`](reflect/construct)

:   The [`new` operator](../operators/new) as a function. Equivalent to
    calling `new target(...argumentsList)`. Also provides the option to
    specify a different prototype.

[`Reflect.defineProperty()`](reflect/defineproperty)

:   Similar to [`Object.defineProperty()`](object/defineproperty).
    Returns a boolean that is `true` if the property was successfully
    defined.

[`Reflect.deleteProperty()`](reflect/deleteproperty)

:   The [`delete` operator](../operators/delete) as a function.
    Equivalent to calling `delete target[propertyKey]`.

[`Reflect.get()`](reflect/get)

:   Returns the value of the property. Works like getting a property
    from an object (`target[propertyKey]`) as a function.

[`Reflect.getOwnPropertyDescriptor()`](reflect/getownpropertydescriptor)

:   Similar to
    [`Object.getOwnPropertyDescriptor()`](object/getownpropertydescriptor).
    Returns a property descriptor of the given property if it exists on
    the object, [`undefined`](undefined) otherwise.

[`Reflect.getPrototypeOf()`](reflect/getprototypeof)

:   Same as [`Object.getPrototypeOf()`](object/getprototypeof).

[`Reflect.has()`](reflect/has)

:   Returns a boolean indicating whether the target has the property.
    Either as own or inherited. Works like the [`in`
    operator](../operators/in) as a function.

[`Reflect.isExtensible()`](reflect/isextensible)

:   Same as [`Object.isExtensible()`](object/isextensible). Returns a
    boolean that is `true` if the target is extensible.

[`Reflect.ownKeys()`](reflect/ownkeys)

:   Returns an array of the target object\'s own (not inherited)
    property keys.

[`Reflect.preventExtensions()`](reflect/preventextensions)

:   Similar to [`Object.preventExtensions()`](object/preventextensions).
    Returns a boolean that is `true` if the update was successful.

[`Reflect.set()`](reflect/set)

:   A function that assigns values to properties. Returns a boolean that
    is `true` if the update was successful.

[`Reflect.setPrototypeOf()`](reflect/setprototypeof)

:   A function that sets the prototype of an object. Returns a boolean
    that is `true` if the update was successful.



 
Examples
--------


 
### Detecting whether an object contains certain properties 

 
 
 
[js]


```js
const duck = {
  name: "Maurice",
  color: "white",
  greeting() {
    console.log(`Quaaaack! My name is ${this.name}`);
  },
};

Reflect.has(duck, "color");
// true
Reflect.has(duck, "haircut");
// false
```




 
### Returning the object\'s own keys 

 
 
 
[js]


```js
Reflect.ownKeys(duck);
// [ "name", "color", "greeting" ]
```




 
### Adding a new property to the object 

 
 
 
[js]


```js
Reflect.set(duck, "eyes", "black");
// returns "true" if successful
// "duck" now contains the property "eyes: 'black'"
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect-object]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect-object)

  ----------------------------------------------------------------------------------------------------


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

`Reflect`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`apply`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`construct`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`defineProperty`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`deleteProperty`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`get`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`getOwnPropertyDescriptor`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`getPrototypeOf`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`has`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`isExtensible`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`ownKeys`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`preventExtensions`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`set`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

`setPrototypeOf`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [`Proxy`](proxy)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect>

