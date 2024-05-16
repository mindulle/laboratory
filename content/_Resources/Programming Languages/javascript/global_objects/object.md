Object
======

 
The `Object` type represents one of [JavaScript\'s data
types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures).
It is used to store various keyed collections and more complex entities.
Objects can be created using the [`Object()`](object/object) constructor
or the [object initializer / literal
syntax](../operators/object_initializer).


 
Description
-----------

 
Nearly all
[objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#objects)
in JavaScript are instances of `Object`; a typical object inherits
properties (including methods) from `Object.prototype`, although these
properties may be shadowed (a.k.a. overridden). The only objects that
don\'t inherit from `Object.prototype` are those with [`null`
prototype](#null-prototype_objects), or descended from other `null`
prototype objects.

Changes to the `Object.prototype` object are seen by **all** objects
through prototype chaining, unless the properties and methods subject to
those changes are overridden further along the prototype chain. This
provides a very powerful although potentially dangerous mechanism to
override or extend object behavior. To make it more secure,
`Object.prototype` is the only object in the core JavaScript language
that has [immutable prototype](object/setprototypeof#description) ---
the prototype of `Object.prototype` is always `null` and not changeable.



 
### Object prototype properties 

 
You should avoid calling any `Object.prototype` method directly from the
instance, especially those that are not intended to be polymorphic (i.e.
only its initial behavior makes sense and no descending object could
override it in a meaningful way). All objects descending from
`Object.prototype` may define a custom own property that has the same
name, but with entirely different semantics from what you expect.
Furthermore, these properties are not inherited by [`null`-prototype
objects](#null-prototype_objects). All modern JavaScript utilities for
working with objects are [static](#static_methods). More specifically:

-   [`valueOf()`](object/valueof), [`toString()`](object/tostring), and
    [`toLocaleString()`](object/tolocalestring) exist to be polymorphic
    and you should expect the object to define its own implementation
    with sensible behaviors, so you can call them as instance methods.
    However, `valueOf()` and `toString()` are usually implicitly called
    through [type
    conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion)
    and you don\'t need to call them yourself in your code.
-   [`__defineGetter__()`](object/__definegetter__),
    [`__defineSetter__()`](object/__definesetter__),
    [`__lookupGetter__()`](object/__lookupgetter__), and
    [`__lookupSetter__()`](object/__lookupsetter__) are deprecated and
    should not be used. Use the static alternatives
    [`Object.defineProperty()`](object/defineproperty) and
    [`Object.getOwnPropertyDescriptor()`](object/getownpropertydescriptor)
    instead.
-   The [`__proto__`](object/proto) property is deprecated and should
    not be used. The [`Object.getPrototypeOf()`](object/getprototypeof)
    and [`Object.setPrototypeOf()`](object/setprototypeof) alternatives
    are static methods.
-   The [`propertyIsEnumerable()`](object/propertyisenumerable) and
    [`hasOwnProperty()`](object/hasownproperty) methods can be replaced
    with the
    [`Object.getOwnPropertyDescriptor()`](object/getownpropertydescriptor)
    and [`Object.hasOwn()`](object/hasown) static methods, respectively.
-   The [`isPrototypeOf()`](object/isprototypeof) method can usually be
    replaced with [`instanceof`](../operators/instanceof), if you are
    checking the `prototype` property of a constructor.

In case where a semantically equivalent static method doesn\'t exist, or
if you really want to use the `Object.prototype` method, you should
directly [`call()`](function/call) the `Object.prototype` method on your
target object instead, to prevent the object from having an overriding
property that produces unexpected results.

 
 
[js]


```js
const obj = {
  foo: 1,
  // You should not define such a method on your own object,
  // but you may not be able to prevent it from happening if
  // you are receiving the object from external input
  propertyIsEnumerable() {
    return false;
  },
};

obj.propertyIsEnumerable("foo"); // false; unexpected result
Object.prototype.propertyIsEnumerable.call(obj, "foo"); // true; expected result
```




 
### Deleting a property from an object 

 
There isn\'t any method in an Object itself to delete its own properties
(such as [`Map.prototype.delete()`](map/delete)). To do so, one must use
the [`delete`](../operators/delete) operator.



 
### null-prototype objects 

 
Almost all objects in JavaScript ultimately inherit from
`Object.prototype` (see [inheritance and the prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)).
However, you may create `null`-prototype objects using
[`Object.create(null)`](object/create) or the [object initializer
syntax](../operators/object_initializer) with `__proto__: null` (note:
the `__proto__` key in object literals is different from the deprecated
[`Object.prototype.__proto__`](object/proto) property). You can also
change the prototype of an existing object to `null` by calling
[`Object.setPrototypeOf(obj, null)`](object/setprototypeof).

 
 
[js]


```js
const obj = Object.create(null);
const obj2 = { __proto__: null };
```


An object with a `null` prototype can behave in unexpected ways, because
it doesn\'t inherit any object methods from `Object.prototype`. This is
especially true when debugging, since common object-property
converting/detecting utility functions may generate errors, or lose
information (especially if using silent error-traps that ignore errors).

For example, the lack of
[`Object.prototype.toString()`](object/tostring) often makes debugging
intractable:

 
 
[js]


```js
const normalObj = {}; // create a normal object
const nullProtoObj = Object.create(null); // create an object with "null" prototype

console.log(`normalObj is: ${normalObj}`); // shows "normalObj is: [object Object]"
console.log(`nullProtoObj is: ${nullProtoObj}`); // throws error: Cannot convert object to primitive value

alert(normalObj); // shows [object Object]
alert(nullProtoObj); // throws error: Cannot convert object to primitive value
```


Other methods will fail as well.

 
 
[js]


```js
normalObj.valueOf(); // shows {}
nullProtoObj.valueOf(); // throws error: nullProtoObj.valueOf is not a function

normalObj.hasOwnProperty("p"); // shows "true"
nullProtoObj.hasOwnProperty("p"); // throws error: nullProtoObj.hasOwnProperty is not a function

normalObj.constructor; // shows "Object() { [native code] }"
nullProtoObj.constructor; // shows "undefined"
```


We can add the `toString` method back to the null-prototype object by
assigning it one:

 
 
[js]


```js
nullProtoObj.toString = Object.prototype.toString; // since new object lacks toString, add the original generic one back

console.log(nullProtoObj.toString()); // shows "[object Object]"
console.log(`nullProtoObj is: ${nullProtoObj}`); // shows "nullProtoObj is: [object Object]"
```


Unlike normal objects, in which `toString()` is on the object\'s
prototype, the `toString()` method here is an own property of
`nullProtoObj`. This is because `nullProtoObj` has no (`null`)
prototype.

You can also revert a null-prototype object back to an ordinary object
using
[`Object.setPrototypeOf(nullProtoObj, Object.prototype)`](object/setprototypeof).

In practice, objects with `null` prototype are usually used as a cheap
substitute for [maps](map). The presence of `Object.prototype`
properties will cause some bugs:

 
 
[js]


```js
const ages = { alice: 18, bob: 27 };

function hasPerson(name) {
  return name in ages;
}

function getAge(name) {
  return ages[name];
}

hasPerson("hasOwnProperty"); // true
getAge("toString"); // [Function: toString]
```


Using a null-prototype object removes this hazard without introducing
too much complexity to the `hasPerson` and `getAge` functions:

 
 
[js]


```js
const ages = Object.create(null, {
  alice: { value: 18, enumerable: true },
  bob: { value: 27, enumerable: true },
});

hasPerson("hasOwnProperty"); // false
getAge("toString"); // undefined
```


In such case, the addition of any method should be done cautiously, as
they can be confused with the other key-value pairs stored as data.

Making your object not inherit from `Object.prototype` also prevents
prototype pollution attacks. If a malicious script adds a property to
`Object.prototype`, it will be accessible on every object in your
program, except objects that have null prototype.

 
 
[js]


```js
const user = {};

// A malicious script:
Object.prototype.authenticated = true;

// Unexpectedly allowing unauthenticated user to pass through
if (user.authenticated) {
  // access confidential data
}
```


JavaScript also has built-in APIs that produce `null`-prototype objects,
especially those that use objects as ad hoc key-value collections. For
example:

-   The return value of [`Object.groupBy()`](object/groupby)
-   The `groups` and `indices.groups` properties of the result of
    [`RegExp.prototype.exec()`](regexp/exec)
-   [`Array.prototype[@@unscopables]`](array/@@unscopables) (all
    `@@unscopables` objects should have `null`-prototype)
-   [`import.meta`](../operators/import.meta)
-   Module namespace objects, obtained through
    [`import * as ns from "module";`](../statements/import#namespace_import)
    or [`import()`](../operators/import)

The term \"`null`-prototype object\" often also includes any object
without `Object.prototype` in its prototype chain. Such objects can be
created with [`extends null`](../classes/extends#extending_null) when
using classes.



 
### Object coercion 

 
Many built-in operations that expect objects first coerce their
arguments to objects. [The
operation](https://tc39.es/ecma262/multipage/abstract-operations.html#sec-toobject)
can be summarized as follows:

-   Objects are returned as-is.
-   [`undefined`](undefined) and [`null`](../operators/null) throw a
    [`TypeError`](typeerror).
-   [`Number`](number), [`String`](string), [`Boolean`](boolean),
    [`Symbol`](symbol), [`BigInt`](bigint) primitives are wrapped into
    their corresponding object wrappers.

There are two ways to achieve nearly the same effect in JavaScript.

-   [`Object.prototype.valueOf()`](object/valueof):
    `Object.prototype.valueOf.call(x)` does exactly the object coercion
    steps explained above to convert `x`.
-   The [`Object()`](object/object) function: `Object(x)` uses the same
    algorithm to convert `x`, except that `undefined` and `null` don\'t
    throw a [`TypeError`](typeerror), but return a plain object.

Places that use object coercion include:

-   The `object` parameter of [`for...in`](../statements/for...in)
    loops.
-   The `this` value of [`Array`](array) methods.
-   Parameters of `Object` methods such as
    [`Object.keys()`](object/keys).
-   Auto-boxing when a property is accessed on a primitive value, since
    primitives do not have properties.
-   The [`this`](../operators/this) value when calling a non-strict
    function. Primitives are boxed while `null` and `undefined` are
    replaced with the [global
    object](https://developer.mozilla.org/en-US/docs/Glossary/Global_object).

Unlike [conversion to
primitives](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion),
the object coercion process itself is not observable in any way, since
it doesn\'t invoke custom code like `toString` or `valueOf` methods.



 
Constructor
-----------

 

[`Object()`](object/object)

:   Turns the input into an object.



 
Static methods 
--------------

 

[`Object.assign()`](object/assign)

:   Copies the values of all enumerable own properties from one or more
    source objects to a target object.

[`Object.create()`](object/create)

:   Creates a new object with the specified prototype object and
    properties.

[`Object.defineProperties()`](object/defineproperties)

:   Adds the named properties described by the given descriptors to an
    object.

[`Object.defineProperty()`](object/defineproperty)

:   Adds the named property described by a given descriptor to an
    object.

[`Object.entries()`](object/entries)

:   Returns an array containing all of the `[key, value]` pairs of a
    given object\'s **own** enumerable string properties.

[`Object.freeze()`](object/freeze)

:   Freezes an object. Other code cannot delete or change its
    properties.

[`Object.fromEntries()`](object/fromentries)

:   Returns a new object from an iterable of `[key, value]` pairs. (This
    is the reverse of [`Object.entries`](object/entries)).

[`Object.getOwnPropertyDescriptor()`](object/getownpropertydescriptor)

:   Returns a property descriptor for a named property on an object.

[`Object.getOwnPropertyDescriptors()`](object/getownpropertydescriptors)

:   Returns an object containing all own property descriptors for an
    object.

[`Object.getOwnPropertyNames()`](object/getownpropertynames)

:   Returns an array containing the names of all of the given object\'s
    **own** enumerable and non-enumerable properties.

[`Object.getOwnPropertySymbols()`](object/getownpropertysymbols)

:   Returns an array of all symbol properties found directly upon a
    given object.

[`Object.getPrototypeOf()`](object/getprototypeof)

:   Returns the prototype (internal `[[Prototype]]` property) of the
    specified object.

[`Object.groupBy()`](object/groupby)

:   Groups the elements of a given iterable according to the string
    values returned by a provided callback function. The returned object
    has separate properties for each group, containing arrays with the
    elements in the group.

[`Object.hasOwn()`](object/hasown)

:   Returns `true` if the specified object has the indicated property as
    its *own* property, or `false` if the property is inherited or does
    not exist.

[`Object.is()`](object/is)

:   Compares if two values are the same value. Equates all `NaN` values
    (which differs from both `IsLooselyEqual` used by
    [`==`](../operators/equality) and `IsStrictlyEqual` used by
    [`===`](../operators/strict_equality)).

[`Object.isExtensible()`](object/isextensible)

:   Determines if extending of an object is allowed.

[`Object.isFrozen()`](object/isfrozen)

:   Determines if an object was frozen.

[`Object.isSealed()`](object/issealed)

:   Determines if an object is sealed.

[`Object.keys()`](object/keys)

:   Returns an array containing the names of all of the given object\'s
    **own** enumerable string properties.

[`Object.preventExtensions()`](object/preventextensions)

:   Prevents any extensions of an object.

[`Object.seal()`](object/seal)

:   Prevents other code from deleting properties of an object.

[`Object.setPrototypeOf()`](object/setprototypeof)

:   Sets the object\'s prototype (its internal `[[Prototype]]`
    property).

[`Object.values()`](object/values)

:   Returns an array containing the values that correspond to all of a
    given object\'s **own** enumerable string properties.



 
Instance properties 
-------------------

 
These properties are defined on `Object.prototype` and shared by all
`Object` instances.

[`Object.prototype.__proto__`](object/proto) [Deprecated]

:   Points to the object which was used as prototype when the object was
    instantiated.

[`Object.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For plain
    `Object` instances, the initial value is the
    [`Object`](object/object) constructor. Instances of other
    constructors each inherit the `constructor` property from their
    respective `Constructor.prototype` object.



 
Instance methods 
----------------

 

[`Object.prototype.__defineGetter__()`](object/__definegetter__) [Deprecated]

:   Associates a function with a property that, when accessed, executes
    that function and returns its return value.

[`Object.prototype.__defineSetter__()`](object/__definesetter__) [Deprecated]

:   Associates a function with a property that, when set, executes that
    function which modifies the property.

[`Object.prototype.__lookupGetter__()`](object/__lookupgetter__) [Deprecated]

:   Returns the function bound as a getter to the specified property.

[`Object.prototype.__lookupSetter__()`](object/__lookupsetter__) [Deprecated]

:   Returns the function bound as a setter to the specified property.

[`Object.prototype.hasOwnProperty()`](object/hasownproperty)

:   Returns a boolean indicating whether an object contains the
    specified property as a direct property of that object and not
    inherited through the prototype chain.

[`Object.prototype.isPrototypeOf()`](object/isprototypeof)

:   Returns a boolean indicating whether the object this method is
    called upon is in the prototype chain of the specified object.

[`Object.prototype.propertyIsEnumerable()`](object/propertyisenumerable)

:   Returns a boolean indicating whether the specified property is the
    object\'s [enumerable
    own](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
    property.

[`Object.prototype.toLocaleString()`](object/tolocalestring)

:   Calls [`toString()`](object/tostring).

[`Object.prototype.toString()`](object/tostring)

:   Returns a string representation of the object.

[`Object.prototype.valueOf()`](object/valueof)

:   Returns the primitive value of the specified object.



 
Examples
--------


 
### Constructing empty objects 

 
The following example creates empty objects using the `new` keyword with
different arguments:

 
 
[js]


```js
const o1 = new Object();
const o2 = new Object(undefined);
const o3 = new Object(null);
```




 
### Using Object() constructor to turn primitives into an Object of their respective type 

 
You can use the [`Object()`](object/object) constructor to create an
object wrapper of a primitive value.

The following examples create variables `o1` and `o2` which are objects
storing [`Boolean`](boolean) and [`BigInt`](bigint) values:

 
 
[js]


```js
// Equivalent to const o1 = new Boolean(true)
const o1 = new Object(true);

// No equivalent because BigInt() can't be called as a constructor,
// and calling it as a regular function won't create an object
const o2 = new Object(1n);
```




 
### Object prototypes 

 
When altering the behavior of existing `Object.prototype` methods,
consider injecting code by wrapping your extension before or after the
existing logic. For example, this (untested) code will pre-conditionally
execute custom logic before the built-in logic or someone else\'s
extension is executed.

When modifying prototypes with hooks, pass `this` and the arguments (the
call state) to the current behavior by calling `apply()` on the
function. This pattern can be used for any prototype, such as
`Node.prototype`, `Function.prototype`, etc.

 
 
[js]


```js
const current = Object.prototype.valueOf;

// Since my property "-prop-value" is cross-cutting and isn't always
// on the same prototype chain, I want to modify Object.prototype:
Object.prototype.valueOf = function (...args) {
  if (Object.hasOwn(this, "-prop-value")) {
    return this["-prop-value"];
  } else {
    // It doesn't look like one of my objects, so let's fall back on
    // the default behavior by reproducing the current behavior as best we can.
    // The apply behaves like "super" in some other languages.
    // Even though valueOf() doesn't take arguments, some other hook may.
    return current.apply(this, args);
  }
};
```


 
**Warning:** Modifying the `prototype` property of any built-in
constructor is considered a bad practice and risks forward
compatibility.


You can read more about prototypes in [Inheritance and the prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain).



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object-objects]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object-objects)

  -------------------------------------------------------------------------------------------------------------


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

`Object`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`Object`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`assign`

45

12

34

32

9

45

34

32

9

5.0

45

1.0

4.0.0

`constructor`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`create`

5

12

4

11.6

5

18

4

12

5

1.0

4.4

1.0

0.10.0

`defineGetter`

1

12

1Starting with Firefox 48, this method can no longer be called at the
global scope without any object. A `TypeError` will be thrown otherwise.
Previously, the global object was used in these cases automatically, but
this is no longer the case.

9.5

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`defineProperties`

5

12

4

11.6

5

18

4

12

5

1.0

4.4

1.0

0.10.0

`defineProperty`

5

12

4

11.6

5.1Also supported in Safari 5, but not on DOM objects.

18

4

12

6Also supported in Safari for iOS 4.2, but not on DOM objects.

1.0

4.4

1.0

0.10.0

`defineSetter`

1

12

1Starting with Firefox 48, this method can no longer be called at the
global scope without any object. A `TypeError` will be thrown otherwise.
Previously, the global object was used in these cases automatically, but
this is no longer the case.

9.5

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`entries`

54

14

47

41

10.1

54

47

41

10.3

6.0

54

1.0

7.0.0

`freeze`

6

12

4

12

5.1

18

4

12

5

1.0

4.4

1.0

0.10.0

`fromEntries`

73

79

63

60

12.1

73

63

52

12.2

11.0

73

1.0

12.0.0

`getOwnPropertyDescriptor`

5

12

4

12

5

18

4

12

5

1.0

4.4

1.0

0.10.0

`getOwnPropertyDescriptors`

54

15

50

41

10

54

50

41

10

6.0

54

1.0

7.0.0

`getOwnPropertyNames`

5

12

4

12

5

18

4

12

5

1.0

4.4

1.0

0.10.0

`getOwnPropertySymbols`

38

12

36

25

9

38

36

25

9

3.0

38

1.0

0.12.0

`getPrototypeOf`

5

12

3.5

12.1

5

18

4

12.1

5

1.0

4.4

1.0

0.10.0

`groupBy`

117

117

119

103

16.4--previewpreview

117

119

78

16.4

No

117

1.37

21.0.0

`hasOwn`

93

93

92

79

15.4

93

92

66

15.4

17.0

93

1.13

16.9.0

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

`is`

19

12

22

15

9

25

22

14

9

1.5

4.4

1.0

0.10.0

`isExtensible`

6

12

4

12

5.1

18

4

12

5

1.0

4.4

1.0

0.10.0

`isFrozen`

6

12

4

12

5.1

18

4

12

5

1.0

4.4

1.0

0.10.0

`isPrototypeOf`

1

12

1

4

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`isSealed`

6

12

4

12

5.1

18

4

12

5

1.0

4.4

1.0

0.10.0

`keys`

5

12

4

12

5

18

4

12

5

1.0

4.4

1.0

0.10.0

`lookupGetter`

1

12

1

9.5

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`lookupSetter`

1

12

1

9.5

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`preventExtensions`

6

12

4

12

5.1

18

4

12

5

1.0

4.4

1.0

0.10.0

`propertyIsEnumerable`

1

12

1

4

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`proto`

1

12

1

10.5

3

18

4

11

1

1.0

4.4

No

0.10.0

`seal`

6

12

4

12

5.1

18

4

12

5

1.0

4.4

1.0

0.10.0

`setPrototypeOf`

34

12

31

21

9

34

31

21

9

2.0

37

1.0

0.12.0

`toLocaleString`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`toString`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`valueOf`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`values`

54

14

47

41

10.1

54

47

41

10.3

6.0

54

1.0

7.0.0

 
See also 
--------

 
-   [Object initializer](../operators/object_initializer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object>

