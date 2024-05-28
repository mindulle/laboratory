[dart:io](../dart-io/dart-io-library){._links-link}

NetworkInterface class
======================

A [NetworkInterface](networkinterface-class) represents an active
network interface on the current system. It contains a list of
[InternetAddress](internetaddress-class)es that are bound to the
interface.

Constructors
------------

[NetworkInterface](networkinterface/networkinterface)()

Properties {#instance-properties}
----------

[addresses](networkinterface/addresses) →
[List](../dart-core/list-class)\<[InternetAddress](internetaddress-class)\>

::: {.features}
read-only
:::

The list of `InternetAddress`es currently bound to this
[NetworkInterface](networkinterface-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[index](networkinterface/index) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The index of the [NetworkInterface](networkinterface-class).

[name](networkinterface/name) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The name of the [NetworkInterface](networkinterface-class).

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

Static Properties
-----------------

[listSupported](networkinterface/listsupported) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the [list](networkinterface/list) method is supported.

Static Methods
--------------

[list](networkinterface/list)({[bool](../dart-core/bool-class) includeLoopback = false, [bool](../dart-core/bool-class) includeLinkLocal = false, [InternetAddressType](internetaddresstype-class) type = InternetAddressType.any}) → [Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[NetworkInterface](networkinterface-class)\>\>
:   Query the system for [NetworkInterface](networkinterface-class)s.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/NetworkInterface-class.html>
:::
