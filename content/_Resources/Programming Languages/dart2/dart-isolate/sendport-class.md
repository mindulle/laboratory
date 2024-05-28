[dart:isolate](../dart-isolate/dart-isolate-library){._links-link}

SendPort class
==============

Sends messages to its [ReceivePort](receiveport-class)s.

[SendPort](sendport-class)s are created from
[ReceivePort](receiveport-class)s. Any message sent through a
[SendPort](sendport-class) is delivered to its corresponding
[ReceivePort](receiveport-class). There might be many
[SendPort](sendport-class)s for the same
[ReceivePort](receiveport-class).

[SendPort](sendport-class)s can be transmitted to other isolates, and
they preserve equality when sent.

Implemented types

:   -   [Capability](capability-class)

Available Extensions

:   -   [NativePort](../dart-ffi/nativeport)

Constructors
------------

[SendPort](sendport/sendport)()

Properties {#instance-properties}
----------

[hashCode](sendport/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

A hash code for this send port that is consistent with the == operator.

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

[send](sendport/send)([Object](../dart-core/object-class)? message) →
void

Sends an asynchronous `message` through this send port, to its
corresponding [ReceivePort](receiveport-class).

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](sendport/operator_equals)([Object](../dart-core/object-class) other)
→ [bool](../dart-core/bool-class)

::: {.features}
override
:::

Tests whether `other` is a [SendPort](sendport-class) pointing to the
same [ReceivePort](receiveport-class) as this one.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/SendPort-class.html>
:::
