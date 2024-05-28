[dart:io](../dart-io/dart-io-library){._links-link}

SocketMessage class
===================

A socket message received by a
[RawDatagramSocket](rawdatagramsocket-class).

A socket message consists of [data](socketmessage/data) bytes and
[controlMessages](socketmessage/controlmessages).

Constructors
------------

[SocketMessage](socketmessage/socketmessage)([Uint8List](../dart-typed_data/uint8list-class)
data,
[List](../dart-core/list-class)\<[SocketControlMessage](socketcontrolmessage-class)\>
controlMessages)

Properties {#instance-properties}
----------

[controlMessages](socketmessage/controlmessages) →
[List](../dart-core/list-class)\<[SocketControlMessage](socketcontrolmessage-class)\>

::: {.features}
final
:::

The control messages sent as part of this socket message.

[data](socketmessage/data) →
[Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
final
:::

The actual bytes of the message.

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
<https://api.dart.dev/stable/2.18.5/dart-io/SocketMessage-class.html>
:::
