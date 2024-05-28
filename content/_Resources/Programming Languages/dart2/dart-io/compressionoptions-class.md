[dart:io](../dart-io/dart-io-library){._links-link}

CompressionOptions class
========================

Options controlling compression in a [WebSocket](websocket-class).

A [CompressionOptions](compressionoptions-class) instance can be passed
to [WebSocket.connect](websocket/connect), or used in other similar
places where [WebSocket](websocket-class) compression is configured.

In most cases the default
[compressionDefault](compressionoptions/compressiondefault-constant) is
sufficient, but in some situations, it might be desirable to use
different compression parameters, for example to preserve memory on
small devices.

Constructors
------------

[CompressionOptions](compressionoptions/compressionoptions)({[bool](../dart-core/bool-class)
clientNoContextTakeover = false, [bool](../dart-core/bool-class)
serverNoContextTakeover = false, [int](../dart-core/int-class)?
clientMaxWindowBits, [int](../dart-core/int-class)? serverMaxWindowBits,
[bool](../dart-core/bool-class) enabled = true})

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[clientMaxWindowBits](compressionoptions/clientmaxwindowbits) →
[int](../dart-core/int-class)?

::: {.features}
final
:::

The maximal window size bit count requested by the client.

[clientNoContextTakeover](compressionoptions/clientnocontexttakeover) →
[bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the client will reuse its compression instances.

[enabled](compressionoptions/enabled) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether WebSocket compression is enabled.

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

[serverMaxWindowBits](compressionoptions/servermaxwindowbits) →
[int](../dart-core/int-class)?

::: {.features}
final
:::

The maximal window size bit count requested by the server.

[serverNoContextTakeover](compressionoptions/servernocontexttakeover) →
[bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the server will reuse its compression instances.

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

Constants
---------

[compressionDefault](compressionoptions/compressiondefault-constant) → const [CompressionOptions](compressionoptions-class)
:   Default [WebSocket](websocket-class) compression configuration.
    <div>

    `CompressionOptions()`

    </div>

[compressionOff](compressionoptions/compressionoff-constant) → const [CompressionOptions](compressionoptions-class)
:   No-compression configuration.
    <div>

    `CompressionOptions(enabled: false)`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/CompressionOptions-class.html>
:::
