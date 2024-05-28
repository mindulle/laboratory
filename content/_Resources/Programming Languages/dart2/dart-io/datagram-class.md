[dart:io](../dart-io/dart-io-library){._links-link}

Datagram class
==============

A data packet received by a
[RawDatagramSocket](rawdatagramsocket-class).

Constructors
------------

[Datagram](datagram/datagram)([Uint8List](../dart-typed_data/uint8list-class)
data, [InternetAddress](internetaddress-class) address,
[int](../dart-core/int-class) port)

Properties {#instance-properties}
----------

[address](datagram/address) ↔ [InternetAddress](internetaddress-class)

::: {.features}
read / write
:::

The address of the socket which sends the data.

[data](datagram/data) ↔ [Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
read / write
:::

The actual bytes of the message.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[port](datagram/port) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The port of the socket which sends the data.

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
<https://api.dart.dev/stable/2.18.5/dart-io/Datagram-class.html>
:::
