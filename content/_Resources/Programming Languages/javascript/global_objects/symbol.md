Symbol
======

 
`Symbol` is a built-in object whose constructor returns a `symbol`
[primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive)
--- also called a **Symbol value** or just a **Symbol** --- that\'s
guaranteed to be unique. Symbols are often used to add unique property
keys to an object that won\'t collide with keys any other code might add
to the object, and which are hidden from any mechanisms other code will
typically use to access the object. That enables a form of weak
[encapsulation](https://developer.mozilla.org/en-US/docs/Glossary/Encapsulation),
or a weak form of [information
hiding](https://en.wikipedia.org/wiki/Information_hiding).

Every `Symbol()` call is guaranteed to return a unique Symbol. Every
`Symbol.for("key")` call will always return the same Symbol for a given
value of `"key"`. When `Symbol.for("key")` is called, if a Symbol with
the given key can be found in the global Symbol registry, that Symbol is
returned. Otherwise, a new Symbol is created, added to the global Symbol
registry under the given key, and returned.


 
Description
-----------

 
To create a new primitive Symbol, you write `Symbol()` with an optional
string as its description:

 
 
[js]


```js
const sym1 = Symbol();
const sym2 = Symbol("foo");
const sym3 = Symbol("foo");
```


The above code creates three new Symbols. Note that `Symbol("foo")` does
not coerce the string `"foo"` into a Symbol. It creates a new Symbol
each time:

 
 
[js]


```js
Symbol("foo") === Symbol("foo"); // false
```


The following syntax with the [`new`](../operators/new) operator will
throw a [`TypeError`](typeerror):

 
 
[js]


```js
const sym = new Symbol(); // TypeError
```


This prevents authors from creating an explicit `Symbol` wrapper object
instead of a new Symbol value and might be surprising as creating
explicit wrapper objects around primitive data types is generally
possible (for example, `new Boolean`, `new String` and `new Number`).

If you really want to create a `Symbol` wrapper object, you can use the
`Object()` function:

 
 
[js]


```js
const sym = Symbol("foo");
typeof sym; // "symbol"
const symObj = Object(sym);
typeof symObj; // "object"
```


Because symbols are the only primitive data type that has reference
identity (that is, you cannot create the same symbol twice), they behave
like objects in some way. For example, they are garbage collectable and
can therefore be stored in [`WeakMap`](weakmap), [`WeakSet`](weakset),
[`WeakRef`](weakref), and [`FinalizationRegistry`](finalizationregistry)
objects.



 
### Shared Symbols in the global Symbol registry 

 
The above syntax using the `Symbol()` function will create a Symbol
whose value remains unique throughout the lifetime of the program. To
create Symbols available across files and even across realms (each of
which has its own global scope), use the methods
[`Symbol.for()`](symbol/for) and [`Symbol.keyFor()`](symbol/keyfor) to
set and retrieve Symbols from the global Symbol registry.

Note that the \"global Symbol registry\" is only a fictitious concept
and may not correspond to any internal data structure in the JavaScript
engine --- and even if such a registry exists, its content is not
available to the JavaScript code, except through the `for()` and
`keyFor()` methods.

The method `Symbol.for(tokenString)` takes a string key and returns a
symbol value from the registry, while `Symbol.keyFor(symbolValue)` takes
a symbol value and returns the string key corresponding to it. Each is
the other\'s inverse, so the following is `true`:

 
 
[js]


```js
Symbol.keyFor(Symbol.for("tokenString")) === "tokenString"; // true
```


Because registered symbols can be arbitrarily created anywhere, they
behave almost exactly like the strings they wrap. Therefore, they are
not guaranteed to be unique and are not garbage collectable. Therefore,
registered symbols are disallowed in [`WeakMap`](weakmap),
[`WeakSet`](weakset), [`WeakRef`](weakref), and
[`FinalizationRegistry`](finalizationregistry) objects.



 
### Well-known Symbols 

 
All static properties of the `Symbol` constructor are Symbols
themselves, whose values are constant across realms. They are known as
*well-known Symbols*, and their purpose is to serve as \"protocols\" for
certain built-in JavaScript operations, allowing users to customize the
language\'s behavior. For example, if a constructor function has a
method with [`Symbol.hasInstance`](symbol/hasinstance) as its name, this
method will encode its behavior with the
[`instanceof`](../operators/instanceof) operator.

Prior to well-known Symbols, JavaScript used normal properties to
implement certain built-in operations. For example, the
[`JSON.stringify`](json/stringify) function will attempt to call each
object\'s `toJSON()` method, and the [`String`](string/string) function
will call the object\'s `toString()` and `valueOf()` methods. However,
as more operations are added to the language, designating each operation
a \"magic property\" can break backward compatibility and make the
language\'s behavior harder to reason with. Well-known Symbols allow the
customizations to be \"invisible\" from normal code, which typically
only read string properties.

In MDN and other sources, well-known symbol values are stylized by
prefixing `@@`. For example, [`Symbol.hasInstance`](symbol/hasinstance)
is written as `@@hasInstance`. This is because symbols don\'t have
actual literal formats, but using `Symbol.hasInstance` does not reflect
the ability of using other aliases to refer to the same symbol. This is
like the difference between `Function.name` and `"Function"`.

Well-known symbols do not have the concept of garbage collectability,
because they come in a fixed set and are unique throughout the lifetime
of the program, similar to intrinsic objects such as `Array.prototype`,
so they are also allowed in [`WeakMap`](weakmap), [`WeakSet`](weakset),
[`WeakRef`](weakref), and [`FinalizationRegistry`](finalizationregistry)
objects.



 
### Finding Symbol properties on objects 

 
The method
[`Object.getOwnPropertySymbols()`](object/getownpropertysymbols) returns
an array of Symbols and lets you find Symbol properties on a given
object. Note that every object is initialized with no own Symbol
properties, so that this array will be empty unless you\'ve set Symbol
properties on the object.



 
Constructor
-----------

 

[`Symbol()`](symbol/symbol)

:   Creates a new `Symbol` object. It is not a constructor in the
    traditional sense, because it can only be called as a function,
    instead of being constructed with `new Symbol()`.



 
Static properties 
-----------------

 
The static properties are all well-known Symbols. In these Symbols\'
descriptions, we will use language like \"`Symbol.hasInstance` is a
method determining...\", but bear in mind that this is referring to the
semantic of an object\'s method having this Symbol as the method name
(because well-known Symbols act as \"protocols\"), not describing the
value of the Symbol itself.

[`Symbol.asyncIterator`](symbol/asynciterator)

:   A method that returns the default AsyncIterator for an object. Used
    by [`for await...of`](../statements/for-await...of).

[`Symbol.hasInstance`](symbol/hasinstance)

:   A method determining if a constructor object recognizes an object as
    its instance. Used by [`instanceof`](../operators/instanceof).

[`Symbol.isConcatSpreadable`](symbol/isconcatspreadable)

:   A Boolean value indicating if an object should be flattened to its
    array elements. Used by [`Array.prototype.concat()`](array/concat).

[`Symbol.iterator`](symbol/iterator)

:   A method returning the default iterator for an object. Used by
    [`for...of`](../statements/for...of).

[`Symbol.match`](symbol/match)

:   A method that matches against a string, also used to determine if an
    object may be used as a regular expression. Used by
    [`String.prototype.match()`](string/match).

[`Symbol.matchAll`](symbol/matchall)

:   A method that returns an iterator, that yields matches of the
    regular expression against a string. Used by
    [`String.prototype.matchAll()`](string/matchall).

[`Symbol.replace`](symbol/replace)

:   A method that replaces matched substrings of a string. Used by
    [`String.prototype.replace()`](string/replace).

[`Symbol.search`](symbol/search)

:   A method that returns the index within a string that matches the
    regular expression. Used by
    [`String.prototype.search()`](string/search).

[`Symbol.species`](symbol/species)

:   A constructor function that is used to create derived objects.

[`Symbol.split`](symbol/split)

:   A method that splits a string at the indices that match a regular
    expression. Used by [`String.prototype.split()`](string/split).

[`Symbol.toPrimitive`](symbol/toprimitive)

:   A method converting an object to a primitive value.

[`Symbol.toStringTag`](symbol/tostringtag)

:   A string value used for the default description of an object. Used
    by [`Object.prototype.toString()`](object/tostring).

[`Symbol.unscopables`](symbol/unscopables)

:   An object value of whose own and inherited property names are
    excluded from the [`with`](../statements/with) environment bindings
    of the associated object.



 
Static methods 
--------------

 

[`Symbol.for()`](symbol/for)

:   Searches for existing Symbols with the given `key` and returns it if
    found. Otherwise a new Symbol gets created in the global Symbol
    registry with `key`.

[`Symbol.keyFor()`](symbol/keyfor)

:   Retrieves a shared Symbol key from the global Symbol registry for
    the given Symbol.



 
Instance properties 
-------------------

 
These properties are defined on `Symbol.prototype` and shared by all
`Symbol` instances.

[`Symbol.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Symbol` instances, the initial value is the
    [`Symbol`](symbol/symbol) constructor.

[`Symbol.prototype.description`](symbol/description)

:   A read-only string containing the description of the Symbol.

[`Symbol.prototype[@@toStringTag]`](#symbol.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Symbol"`. This property is used in
    [`Object.prototype.toString()`](object/tostring). However, because
    `Symbol` also has its own [`toString()`](symbol/tostring) method,
    this property is not used unless you call
    [`Object.prototype.toString.call()`](function/call) with a symbol as
    `thisArg`.



 
Instance methods 
----------------

 

[`Symbol.prototype.toString()`](symbol/tostring)

:   Returns a string containing the description of the Symbol. Overrides
    the [`Object.prototype.toString()`](object/tostring) method.

[`Symbol.prototype.valueOf()`](symbol/valueof)

:   Returns the Symbol. Overrides the
    [`Object.prototype.valueOf()`](object/valueof) method.

[`Symbol.prototype[@@toPrimitive]()`](symbol/@@toprimitive)

:   Returns the Symbol.



 
Examples
--------


 
### Using the typeof operator with Symbols 

 
The [`typeof`](../operators/typeof) operator can help you to identify
Symbols.

 
 
[js]


```js
typeof Symbol() === "symbol";
typeof Symbol("foo") === "symbol";
typeof Symbol.iterator === "symbol";
```




 
### Symbol type conversions 

 
Some things to note when working with type conversion of Symbols.

-   When trying to convert a Symbol to a number, a
    [`TypeError`](typeerror) will be thrown (e.g. `+sym` or `sym | 0`).
-   When using loose equality, `Object(sym) == sym` returns `true`.
-   `Symbol("foo") + "bar"` throws a [`TypeError`](typeerror) (can\'t
    convert Symbol to string). This prevents you from silently creating
    a new string property name from a Symbol, for example.
-   The [\"safer\" `String(sym)` conversion](string#string_conversion)
    works like a call to
    [`Symbol.prototype.toString()`](symbol/tostring) with Symbols, but
    note that `new String(sym)` will throw.



 
### Symbols and for\...in iteration 

 
Symbols are not enumerable in [`for...in`](../statements/for...in)
iterations. In addition,
[`Object.getOwnPropertyNames()`](object/getownpropertynames) will not
return Symbol object properties, however, you can use
[`Object.getOwnPropertySymbols()`](object/getownpropertysymbols) to get
these.

 
 
[js]


```js
const obj = {};

obj[Symbol("a")] = "a";
obj[Symbol.for("b")] = "b";
obj["c"] = "c";
obj.d = "d";

for (const i in obj) {
  console.log(i);
}
// "c" "d"
```




 
### Symbols and JSON.stringify() 

 
Symbol-keyed properties will be completely ignored when using
`JSON.stringify()`:

 
 
[js]


```js
JSON.stringify({ [Symbol("foo")]: "foo" });
// '{}'
```


For more details, see [`JSON.stringify()`](json/stringify).



 
### Symbol wrapper objects as property keys 

 
When a Symbol wrapper object is used as a property key, this object will
be coerced to its wrapped Symbol:

 
 
[js]


```js
const sym = Symbol("foo");
const obj = { [sym]: 1 };
obj[sym]; // 1
obj[Object(sym)]; // still 1
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol-objects]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol-objects)

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

`@@toPrimitive`

47

15

44

34

10

47

44

34

10

5.0

47

1.0

6.0.0

`Symbol`

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

`Symbol`

38

12Edge 12 included Symbol properties in `JSON.stringify()` output.

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

`asyncIterator`

63

79

57

50

11.1

63

57

46

11.3

8.0

63

1.0

10.0.0

`description`

70

79

63

57

12.1

12No support for an undefined description.

70

63

49

12.2

12No support for an undefined description.

10.0

70

1.0

11.0.0

`for`

40

12

36

27

9

40

36

27

9

4.0

40

1.0

0.12.0

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

`isConcatSpreadable`

48

15

48

35

10

48

48

35

10

5.0

48

1.0

6.0.0

`iterator`

43

12

36

30

10

43

36

30

10

4.0

43

1.0

0.12.0

`keyFor`

40

12

36

27

9

40

36

27

9

4.0

40

1.0

0.12.0

`match`

50

79

40

37

10

50

40

37

10

5.0

50

1.0

6.0.0

`matchAll`

73

79

67

60

13

73

67

52

13

11.0

73

1.0

12.0.0

`replace`

50

79

49

37

10

50

49

37

10

5.0

50

1.0

6.0.0

`search`

50

79

49

37

10

50

49

37

10

5.0

50

1.0

6.0.0

`species`

51

13

41

38

10

51

41

41

10

5.0

51

1.0

6.5.0

`split`

50

79

49

37

10

50

49

37

10

5.0

50

1.0

6.0.0

`toPrimitive`

47

15

44

34

10

47

44

34

10

5.0

47

1.0

6.0.0

`toString`

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

`toStringTag`

49

15

51

36

10

49

51

36

10

5.0

49

1.0

6.0.0

`unscopables`

38

12

48

25

9

38

48

25

9

3.0

38

1.0

0.12.0

`valueOf`

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

 
See also 
--------

 
-   [Polyfill of `Symbol` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`typeof`](../operators/typeof)
-   [JavaScript data types and data
    structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
-   [ES6 In Depth:
    Symbols](https://hacks.mozilla.org/2015/06/es6-in-depth-symbols/) on
    hacks.mozilla.org (2015)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol>

