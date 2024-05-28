[dart:isolate](../dart-isolate/dart-isolate-library){._links-link}

Capability class
================

An unforgeable object that comes back as equal when passed through other
isolates.

Sending a capability object to another isolate, and getting it back,
will produce an object that is equal to the original. There is no other
way to create objects equal to a capability object.

Capabilities can be used as access guards. An isolate can receive
requests for operations from other isolates, but only allow them if the
request contains the correct capability object. This allows exposing the
same interface to multiple clients, but restricting some operations to
only those clients that have also been given the corresponding
capability.

Capabilities can be used inside a single isolate, but they have no
advantage over just using `Object()` to create a unique object, and it
offers no real security against other code running in the same isolate.

Implementers

:   -   [SendPort](sendport-class)

Constructors
------------

[Capability](capability/capability)()

::: {.constructor-modifier .features}
factory
:::

Create a new unforgeable capability object.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

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

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Capability-class.html>
:::
