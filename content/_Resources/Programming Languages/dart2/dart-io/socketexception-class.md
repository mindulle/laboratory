[dart:io](../dart-io/dart-io-library){._links-link}

SocketException class
=====================

Exception thrown when a socket operation fails.

Implemented types

:   -   [IOException](ioexception-class)

Constructors
------------

[SocketException](socketexception/socketexception)([String](../dart-core/string-class)
message, {[OSError](oserror-class)? osError,
[InternetAddress](internetaddress-class)? address,
[int](../dart-core/int-class)? port})

::: {.constructor-modifier .features}
const
:::

Creates a [SocketException](socketexception-class) with the provided
values.

[SocketException.closed](socketexception/socketexception.closed)()

::: {.constructor-modifier .features}
const
:::

Creates an exception reporting that a socket was used after it was
closed.

Properties {#instance-properties}
----------

[address](socketexception/address) →
[InternetAddress](internetaddress-class)?

::: {.features}
final
:::

The address of the socket giving rise to the exception.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](socketexception/message) → [String](../dart-core/string-class)

::: {.features}
final
:::

Description of the error.

[osError](socketexception/oserror) → [OSError](oserror-class)?

::: {.features}
final
:::

The underlying OS error.

[port](socketexception/port) → [int](../dart-core/int-class)?

::: {.features}
final
:::

The port of the socket giving rise to the exception.

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

[toString](socketexception/tostring)() →
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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketException-class.html>
:::
