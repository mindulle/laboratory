[dart:core](../dart-core/dart-core-library){._links-link}

Function class
==============

The base class for all function types.

The run-time type of a function object is subtype of a function type,
and as such, a subtype of [Function](function-class).

Constructors
------------

[Function](function/function)()

Properties {#instance-properties}
----------

[hashCode](function/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

A hash code value that is compatible with `operator==`.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](function/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Test whether another object is equal to this function.

Static Methods
--------------

[apply](function/apply)([Function](function-class) function, [List](list-class)? positionalArguments, \[[Map](map-class)\<[Symbol](symbol-class), dynamic\>? namedArguments\]) → dynamic
:   Dynamically call `function` with the specified arguments.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Function-class.html>
:::
