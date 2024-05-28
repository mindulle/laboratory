[dart:isolate](../dart-isolate/dart-isolate-library){._links-link}

RawReceivePort class
====================

A low-level asynchronous message receiver.

A [RawReceivePort](rawreceiveport-class) is low level feature, and is
not [Zone](../dart-async/zone-class) aware. The
[handler](rawreceiveport/handler) will always be invoked in the
[Zone.root](../dart-async/zone/root-constant) zone.

The port cannot be paused. The data-handler must be set before the first
message is received, otherwise the message is lost.

Messages can be sent to this port using
[sendPort](rawreceiveport/sendport).

Constructors
------------

[RawReceivePort](rawreceiveport/rawreceiveport)(\[[Function](../dart-core/function-class)?
handler, [String](../dart-core/string-class) debugName = \'\'\])

::: {.constructor-modifier .features}
factory
:::

Opens a long-lived port for receiving messages.

Properties {#instance-properties}
----------

[handler](rawreceiveport/handler) ←
[Function](../dart-core/function-class)?

::: {.features}
write-only
:::

Sets the handler that is invoked for every incoming message.

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

[sendPort](rawreceiveport/sendport) → [SendPort](sendport-class)

::: {.features}
read-only
:::

Returns a [SendPort](sendport-class) that sends messages to this raw
receive port.

Methods {#instance-methods}
-------

[close](rawreceiveport/close)() → void

Closes the port.

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
<https://api.dart.dev/stable/2.18.5/dart-isolate/RawReceivePort-class.html>
:::
