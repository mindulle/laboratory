[dart:io](../dart-io/dart-io-library){._links-link}

SocketControlMessage class
==========================

Control message part of the [SocketMessage](socketmessage-class)
received by a call to [RawSocket.readMessage](rawsocket/readmessage).

Control messages could carry different information including
[ResourceHandle](resourcehandle-class). If
[ResourceHandle](resourcehandle-class)s are availabe as part of this
message, they can be extracted via
[extractHandles](socketcontrolmessage/extracthandles).

Constructors
------------

[SocketControlMessage.fromHandles](socketcontrolmessage/socketcontrolmessage.fromhandles)([List](../dart-core/list-class)\<[ResourceHandle](resourcehandle-class)\>
handles)

::: {.constructor-modifier .features}
factory
:::

Creates a control message containing the provided `handles`.

Properties {#instance-properties}
----------

[data](socketcontrolmessage/data) →
[Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
read-only
:::

Actual bytes that were passed as part of the control message by the
underlying platform.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[level](socketcontrolmessage/level) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

A platform specific value used to determine the kind of control message.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[type](socketcontrolmessage/type) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

A platform specific value used to determine the kind of control message.

Methods {#instance-methods}
-------

[extractHandles](socketcontrolmessage/extracthandles)() →
[List](../dart-core/list-class)\<[ResourceHandle](resourcehandle-class)\>

Extracts the list of handles embedded in this message.

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
<https://api.dart.dev/stable/2.18.5/dart-io/SocketControlMessage-class.html>
:::
