[dart:io](../dart-io/dart-io-library){._links-link}

InternetAddressType class
=========================

The type, or address family, of an
[InternetAddress](internetaddress-class).

Currently, IP version 4 (IPv4), IP version 6 (IPv6) and Unix domain
address are supported. Unix domain sockets are available only on Linux,
MacOS and Android.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[name](internetaddresstype/name) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

Get the name of the type, e.g. \"IPv4\" or \"IPv6\".

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

[toString](internetaddresstype/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
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

Constants
---------

[any](internetaddresstype/any-constant) → const
[InternetAddressType](internetaddresstype-class)

<div>

`const InternetAddressType._(-1)`

</div>

[IPv4](internetaddresstype/ipv4-constant) → const
[InternetAddressType](internetaddresstype-class)

<div>

`const InternetAddressType._(0)`

</div>

[IPv6](internetaddresstype/ipv6-constant) → const
[InternetAddressType](internetaddresstype-class)

<div>

`const InternetAddressType._(1)`

</div>

[unix](internetaddresstype/unix-constant) → const
[InternetAddressType](internetaddresstype-class)

::: {.features}
\@Since(\"2.8\")
:::

<div>

`const InternetAddressType._(2)`

</div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddressType-class.html>
:::
