TypeError: \"x\" is not a non-null object
=========================================

 
The JavaScript exception \"is not a non-null object\" occurs when an
object is expected somewhere and wasn\'t provided.
[`null`](../operators/null) is not an object and won\'t work.


 
Message
-------

 
```text
TypeError: Property description must be an object: x (V8-based)
TypeError: Property descriptor must be an object, got "x" (Firefox)
TypeError: Property description must be an object. (Safari)

TypeError: Invalid value used in weak set (V8-based)
TypeError: WeakSet value must be an object, got "x" (Firefox)
TypeError: Attempted to add a non-object value to a WeakSet (Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror)



 
What went wrong? 
----------------

 
An object is expected somewhere and wasn\'t provided.
[`null`](../operators/null) is not an object and won\'t work. You must
provide a proper object in the given situation.



 
Examples
--------


 
### Property descriptor expected 

 
When methods like [`Object.create()`](../global_objects/object/create)
or [`Object.defineProperty()`](../global_objects/object/defineproperty)
and
[`Object.defineProperties()`](../global_objects/object/defineproperties)
are used, the optional descriptor parameter expects a property
descriptor object. Providing no object (like just a number), will throw
an error:

 
 
[js]


```js
Object.defineProperty({}, "key", 1);
// TypeError: 1 is not a non-null object

Object.defineProperty({}, "key", null);
// TypeError: null is not a non-null object
```


A valid property descriptor object might look like this:

 
 
[js]


```js
Object.defineProperty({}, "key", { value: "foo", writable: false });
```




 
### WeakMap and WeakSet objects require object or symbol keys 

 
[`WeakMap`](../global_objects/weakmap) and
[`WeakSet`](../global_objects/weakset) objects store object or symbol
keys. You can\'t use other types as keys.

 
 
[js]


```js
const ws = new WeakSet();
ws.add("foo");
// TypeError: "foo" is not a non-null object
```


Use objects instead:

 
 
[js]


```js
ws.add({ foo: "bar" });
ws.add(window);
```




 
See also 
--------

 
-   [`Object.create()`](../global_objects/object/create)
-   [`Object.defineProperty()`](../global_objects/object/defineproperty)
-   [`Object.defineProperties()`](../global_objects/object/defineproperties)
-   [`WeakMap`](../global_objects/weakmap)
-   [`WeakSet`](../global_objects/weakset)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_non-null_object>

