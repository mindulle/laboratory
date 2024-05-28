[dart:io](../dart-io/dart-io-library){._links-link}

ResourceHandle class
====================

A wrappper around OS resource handle so it can be passed via Socket as
part of [SocketMessage](socketmessage-class).

Constructors
------------

[ResourceHandle.fromFile](resourcehandle/resourcehandle.fromfile)([RandomAccessFile](randomaccessfile-class)
file)

::: {.constructor-modifier .features}
factory
:::

Creates wrapper around opened file.

[ResourceHandle.fromRawDatagramSocket](resourcehandle/resourcehandle.fromrawdatagramsocket)([RawDatagramSocket](rawdatagramsocket-class)
socket)

::: {.constructor-modifier .features}
factory
:::

Creates wrapper around opened raw datagram socket.

[ResourceHandle.fromRawSocket](resourcehandle/resourcehandle.fromrawsocket)([RawSocket](rawsocket-class)
socket)

::: {.constructor-modifier .features}
factory
:::

Creates wrapper around opened raw socket.

[ResourceHandle.fromSocket](resourcehandle/resourcehandle.fromsocket)([Socket](socket-class)
socket)

::: {.constructor-modifier .features}
factory
:::

Creates wrapper around opened socket.

[ResourceHandle.fromStdin](resourcehandle/resourcehandle.fromstdin)([Stdin](stdin-class)
stdin)

::: {.constructor-modifier .features}
factory
:::

Creates wrapper around current stdin.

[ResourceHandle.fromStdout](resourcehandle/resourcehandle.fromstdout)([Stdout](stdout-class)
stdout)

::: {.constructor-modifier .features}
factory
:::

Creates wrapper around current stdout.

Properties {#instance-properties}
----------

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

[toFile](resourcehandle/tofile)() →
[RandomAccessFile](randomaccessfile-class)

Extracts opened file from resource handle.

[toRawDatagramSocket](resourcehandle/torawdatagramsocket)() →
[RawDatagramSocket](rawdatagramsocket-class)

Extracts opened raw datagram socket from resource handle.

[toRawSocket](resourcehandle/torawsocket)() →
[RawSocket](rawsocket-class)

Extracts opened raw socket from resource handle.

[toSocket](resourcehandle/tosocket)() → [Socket](socket-class)

Extracts opened socket from resource handle.

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
<https://api.dart.dev/stable/2.18.5/dart-io/ResourceHandle-class.html>
:::
