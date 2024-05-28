[dart:js](../dart-js/dart-js-library){._links-link}

JsFunction class
================

A proxy on a JavaScript Function object.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [JsObject](jsobject-class)
    -   JsFunction

Constructors
------------

[JsFunction.withThis](jsfunction/jsfunction.withthis)([Function](../dart-core/function-class)
f)

::: {.constructor-modifier .features}
factory
:::

Returns a [JsFunction](jsfunction-class) that captures its \'this\'
binding and calls `f` with the value of JavaScript `this` passed as the
first argument.

Properties {#instance-properties}
----------

[hashCode](jsobject/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
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

[apply](jsfunction/apply)([List](../dart-core/list-class) args, {dynamic
thisArg}) → dynamic

Invokes the JavaScript function with arguments `args`. If `thisArg` is
supplied it is the value of `this` for the invocation.

[callMethod](jsobject/callmethod)([Object](../dart-core/object-class)
method, \[[List](../dart-core/list-class)? args\]) → dynamic

::: {.features}
inherited
:::

Calls `method` on the JavaScript object with the arguments `args` and
returns the result.

[deleteProperty](jsobject/deleteproperty)([Object](../dart-core/object-class)
property) → void

::: {.features}
inherited
:::

Removes `property` from the JavaScript object.

[hasProperty](jsobject/hasproperty)([Object](../dart-core/object-class)
property) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns `true` if the JavaScript object contains the specified property
either directly or though its prototype chain.

[instanceof](jsobject/instanceof)([JsFunction](jsfunction-class) type) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

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
inherited
:::

Returns the result of the JavaScript objects `toString` method.

Operators
---------

[operator
==](jsobject/operator_equals)([Object](../dart-core/object-class) other)
→ [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](jsobject/operator_get)([Object](../dart-core/object-class)
property) → dynamic

::: {.features}
inherited
:::

Returns the value associated with `property` from the proxied JavaScript
object.

[operator
\[\]=](jsobject/operator_put)([Object](../dart-core/object-class)
property, [Object](../dart-core/object-class)? value) → void

::: {.features}
inherited
:::

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsFunction-class.html>
:::
