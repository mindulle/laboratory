[dart:io](../dart-io/dart-io-library){._links-link}

InternetAddress class
=====================

An internet address or a Unix domain address.

This object holds an internet address. If this internet address is the
result of a DNS lookup, the address also holds the hostname used to make
the lookup. An Internet address combined with a port number represents
an endpoint to which a socket can connect or a listening socket can
bind.

Constructors
------------

[InternetAddress](internetaddress/internetaddress)([String](../dart-core/string-class)
address, {\@Since(\"2.8\")
[InternetAddressType](internetaddresstype-class)? type})

::: {.constructor-modifier .features}
factory
:::

Creates a new [InternetAddress](internetaddress-class) from a numeric
address or a file path.

[InternetAddress.fromRawAddress](internetaddress/internetaddress.fromrawaddress)([Uint8List](../dart-typed_data/uint8list-class)
rawAddress, {\@Since(\"2.8\")
[InternetAddressType](internetaddresstype-class)? type})

::: {.constructor-modifier .features}
factory
:::

Creates a new [InternetAddress](internetaddress-class) from the provided
raw address bytes.

Properties {#instance-properties}
----------

[address](internetaddress/address) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The numeric address of the host.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[host](internetaddress/host) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The host used to lookup the address.

[isLinkLocal](internetaddress/islinklocal) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the scope of the [InternetAddress](internetaddress-class) is a
link-local.

[isLoopback](internetaddress/isloopback) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the [InternetAddress](internetaddress-class) is a loopback
address.

[isMulticast](internetaddress/ismulticast) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the scope of the [InternetAddress](internetaddress-class) is
multicast.

[rawAddress](internetaddress/rawaddress) →
[Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
read-only
:::

The raw address of this [InternetAddress](internetaddress-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[type](internetaddress/type) →
[InternetAddressType](internetaddresstype-class)

::: {.features}
read-only
:::

The address family of the [InternetAddress](internetaddress-class).

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reverse](internetaddress/reverse)() →
[Future](../dart-async/future-class)\<[InternetAddress](internetaddress-class)\>

Performs a reverse DNS lookup on this [address](internetaddress/address)

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

[anyIPv4](internetaddress/anyipv4) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

IP version 4 any address.

[anyIPv6](internetaddress/anyipv6) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

IP version 6 any address.

[loopbackIPv4](internetaddress/loopbackipv4) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

IP version 4 loopback address.

[loopbackIPv6](internetaddress/loopbackipv6) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

IP version 6 loopback address.

Static Methods
--------------

[lookup](internetaddress/lookup)([String](../dart-core/string-class) host, {[InternetAddressType](internetaddresstype-class) type = InternetAddressType.any}) → [Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[InternetAddress](internetaddress-class)\>\>
:   Looks up the addresses of a host.

[tryParse](internetaddress/tryparse)([String](../dart-core/string-class) address) → [InternetAddress](internetaddress-class)?
:   Attempts to parse `address` as a numeric address.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddress-class.html>
:::
