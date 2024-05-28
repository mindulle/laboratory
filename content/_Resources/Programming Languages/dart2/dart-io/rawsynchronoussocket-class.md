[dart:io](../dart-io/dart-io-library){._links-link}

RawSynchronousSocket class
==========================

A low-level class for communicating synchronously over a TCP socket.

Warning: [RawSynchronousSocket](rawsynchronoussocket-class) should
probably only be used to connect to \'localhost\'. The operations below
will block the calling thread to wait for a response from the network.
The thread can process no other events while waiting for these
operations to complete.
[RawSynchronousSocket](rawsynchronoussocket-class) is not suitable for
applications that require high performance or asynchronous I/O such as a
server. Instead such applications should use the non-blocking sockets
and asynchronous operations in the [Socket](socket-class) or
[RawSocket](rawsocket-class) classes.

Constructors
------------

[RawSynchronousSocket](rawsynchronoussocket/rawsynchronoussocket)()

Properties {#instance-properties}
----------

[address](rawsynchronoussocket/address) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

The [InternetAddress](internetaddress-class) used to connect this
socket.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[port](rawsynchronoussocket/port) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The port used by this socket.

[remoteAddress](rawsynchronoussocket/remoteaddress) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

The remote [InternetAddress](internetaddress-class) connected to by this
socket.

[remotePort](rawsynchronoussocket/remoteport) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

The remote port connected to by this socket.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[available](rawsynchronoussocket/available)() →
[int](../dart-core/int-class)

The number of received and unread bytes in the socket that can be read.

[closeSync](rawsynchronoussocket/closesync)() → void

Closes the [RawSynchronousSocket](rawsynchronoussocket-class).

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[readIntoSync](rawsynchronoussocket/readintosync)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) → [int](../dart-core/int-class)

Reads bytes into an existing `buffer`.

[readSync](rawsynchronoussocket/readsync)([int](../dart-core/int-class)
bytes) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?

Reads up to `bytes` bytes from the socket.

[shutdown](rawsynchronoussocket/shutdown)([SocketDirection](socketdirection-class)
direction) → void

Shuts down a socket in the provided direction.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[writeFromSync](rawsynchronoussocket/writefromsync)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) → void

Writes from a `buffer` to the socket.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[connectSync](rawsynchronoussocket/connectsync)(dynamic host, [int](../dart-core/int-class) port) → [RawSynchronousSocket](rawsynchronoussocket-class)
:   Creates a new socket connection and returns a
    [RawSynchronousSocket](rawsynchronoussocket-class).

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSynchronousSocket-class.html>
:::
