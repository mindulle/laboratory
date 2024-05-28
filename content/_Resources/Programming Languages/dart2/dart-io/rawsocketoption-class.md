[dart:io](../dart-io/dart-io-library){._links-link}

RawSocketOption class
=====================

The [RawSocketOption](rawsocketoption-class) is used as a parameter to
[Socket.setRawOption](socket/setrawoption) and
[RawSocket.setRawOption](rawsocket/setrawoption) to customize the
behaviour of the underlying socket.

It allows for fine grained control of the socket options, and its values
will be passed to the underlying platform\'s implementation of
setsockopt and getsockopt.

Annotations

:   -   \@Since(\"2.2\")

Constructors
------------

[RawSocketOption](rawsocketoption/rawsocketoption)([int](../dart-core/int-class)
level, [int](../dart-core/int-class) option,
[Uint8List](../dart-typed_data/uint8list-class) value)

::: {.constructor-modifier .features}
const
:::

Creates a [RawSocketOption](rawsocketoption-class) for
[RawSocket.getRawOption](rawsocket/getrawoption) and
[RawSocket.setRawOption](rawsocket/setrawoption).

[RawSocketOption.fromBool](rawsocketoption/rawsocketoption.frombool)([int](../dart-core/int-class)
level, [int](../dart-core/int-class) option,
[bool](../dart-core/bool-class) value)

::: {.constructor-modifier .features}
factory
:::

Convenience constructor for creating a boolean based
[RawSocketOption](rawsocketoption-class).

[RawSocketOption.fromInt](rawsocketoption/rawsocketoption.fromint)([int](../dart-core/int-class)
level, [int](../dart-core/int-class) option,
[int](../dart-core/int-class) value)

::: {.constructor-modifier .features}
factory
:::

Convenience constructor for creating an integer based
[RawSocketOption](rawsocketoption-class).

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[level](rawsocketoption/level) → [int](../dart-core/int-class)

::: {.features}
final
:::

The level for the option to set or get.

[option](rawsocketoption/option) → [int](../dart-core/int-class)

::: {.features}
final
:::

The numeric ID of the option to set or get.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[value](rawsocketoption/value) →
[Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
final
:::

The raw data to set, or the array to write the current option value
into.

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

Static Properties
-----------------

[IPv4MulticastInterface](rawsocketoption/ipv4multicastinterface) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

Socket option for `IP_MULTICAST_IF`.

[IPv6MulticastInterface](rawsocketoption/ipv6multicastinterface) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

Socket option for `IPV6_MULTICAST_IF`.

[levelIPv4](rawsocketoption/levelipv4) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Socket level option for `IPPROTO_IP`.

[levelIPv6](rawsocketoption/levelipv6) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Socket level option for `IPPROTO_IPV6`.

[levelSocket](rawsocketoption/levelsocket) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

Socket level option for `SOL_SOCKET`.

[levelTcp](rawsocketoption/leveltcp) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Socket level option for `IPPROTO_TCP`.

[levelUdp](rawsocketoption/leveludp) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Socket level option for `IPPROTO_UDP`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption-class.html>
:::
