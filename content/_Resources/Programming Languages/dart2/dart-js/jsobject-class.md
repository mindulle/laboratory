[dart:js](../dart-js/dart-js-library){._links-link}

JsObject class
==============

A proxy on a JavaScript object.

The properties of the JavaScript object are accessible via the `[]` and
`[]=` operators. Methods are callable via
[callMethod](jsobject/callmethod).

Implementers

:   -   [JsArray](jsarray-class)
    -   [JsFunction](jsfunction-class)

Constructors
------------

[JsObject](jsobject/jsobject)([JsFunction](jsfunction-class)
constructor, \[[List](../dart-core/list-class)? arguments\])

::: {.constructor-modifier .features}
factory
:::

Constructs a JavaScript object from its native `constructor` and returns
a proxy to it.

[JsObject.fromBrowserObject](jsobject/jsobject.frombrowserobject)([Object](../dart-core/object-class)
object)

::: {.constructor-modifier .features}
factory
:::

Constructs a [JsObject](jsobject-class) that proxies a native Dart
object; *for expert use only*.

[JsObject.jsify](jsobject/jsobject.jsify)([Object](../dart-core/object-class)
object)

::: {.constructor-modifier .features}
factory
:::

Recursively converts a JSON-like collection of Dart objects to a
collection of JavaScript objects and returns a
[JsObject](jsobject-class) proxy to it.

Properties {#instance-properties}
----------

[hashCode](jsobject/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[callMethod](jsobject/callmethod)([Object](../dart-core/object-class)
method, \[[List](../dart-core/list-class)? args\]) → dynamic

Calls `method` on the JavaScript object with the arguments `args` and
returns the result.

[deleteProperty](jsobject/deleteproperty)([Object](../dart-core/object-class)
property) → void

Removes `property` from the JavaScript object.

[hasProperty](jsobject/hasproperty)([Object](../dart-core/object-class)
property) → [bool](../dart-core/bool-class)

Returns `true` if the JavaScript object contains the specified property
either directly or though its prototype chain.

[instanceof](jsobject/instanceof)([JsFunction](jsfunction-class) type) →
[bool](../dart-core/bool-class)

Returns `true` if the JavaScript object has `type` in its prototype
chain.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](jsobject/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

Returns the result of the JavaScript objects `toString` method.

Operators
---------

[operator
==](jsobject/operator_equals)([Object](../dart-core/object-class) other)
→ [bool](../dart-core/bool-class)

::: {.features}
override
:::

The equality operator.

[operator
\[\]](jsobject/operator_get)([Object](../dart-core/object-class)
property) → dynamic

Returns the value associated with `property` from the proxied JavaScript
object.

[operator
\[\]=](jsobject/operator_put)([Object](../dart-core/object-class)
property, [Object](../dart-core/object-class)? value) → void

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsObject-class.html>
:::
