[dart:io](../dart-io/dart-io-library){._links-link}

RawSecureSocket class
=====================

`RawSecureSocket` provides a secure (SSL or TLS) network connection.

Client connections to a server are provided by calling
RawSecureSocket.connect. A secure server, created with
[RawSecureServerSocket](rawsecureserversocket-class), also returns
`RawSecureSocket` objects representing the server end of a secure
connection. The certificate provided by the server is checked using the
trusted certificates set in the [SecurityContext](securitycontext-class)
object. The default [SecurityContext](securitycontext-class) object
contains a built-in set of trusted root certificates for well-known
certificate authorities.

Implemented types

:   -   [RawSocket](rawsocket-class)

Constructors
------------

[RawSecureSocket](rawsecuresocket/rawsecuresocket)()

Properties {#instance-properties}
----------

[address](rawsocket/address) → [InternetAddress](internetaddress-class)

::: {.features}
read-only, inherited
:::

The [InternetAddress](internetaddress-class) used to connect this
socket.

[first](../dart-async/stream/first) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
read-only, inherited
:::

The first element of this stream.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isBroadcast](../dart-async/stream/isbroadcast) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this stream is a broadcast stream.

[isEmpty](../dart-async/stream/isempty) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
read-only, inherited
:::

Whether this stream contains any elements.

[last](../dart-async/stream/last) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
read-only, inherited
:::

The last element of this stream.

[length](../dart-async/stream/length) →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

::: {.features}
read-only, inherited
:::

The number of elements in this stream.

[peerCertificate](rawsecuresocket/peercertificate) →
[X509Certificate](x509certificate-class)?

::: {.features}
read-only
:::

Get the peer certificate for a connected RawSecureSocket. If this
RawSecureSocket is the server end of a secure socket connection,
[peerCertificate](rawsecuresocket/peercertificate) will return the
client certificate, or null, if no client certificate was received. If
it is the client end, [peerCertificate](rawsecuresocket/peercertificate)
will return the server\'s certificate.

[port](rawsocket/port) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The port used by this socket.

[readEventsEnabled](rawsocket/readeventsenabled) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write, inherited
:::

Set or get, if the [RawSocket](rawsocket-class) should listen for
[RawSocketEvent.read](rawsocketevent/read-constant) events. Default is
`true`.

[remoteAddress](rawsocket/remoteaddress) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only, inherited
:::

The remote [InternetAddress](internetaddress-class) connected to by this
socket.

[remotePort](rawsocket/remoteport) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The remote port connected to by this socket.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[selectedProtocol](rawsecuresocket/selectedprotocol) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

The protocol which was selected during protocol negotiation.

[single](../dart-async/stream/single) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
read-only, inherited
:::

The single element of this stream.

[writeEventsEnabled](rawsocket/writeeventsenabled) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write, inherited
:::

Set or get, if the [RawSocket](rawsocket-class) should listen for
[RawSocketEvent.write](rawsocketevent/write-constant) events. Default is
`true`. This is a one-shot listener, and writeEventsEnabled must be set
to true again to receive another write event.

Methods {#instance-methods}
-------

[any](../dart-async/stream/any)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](../dart-async/stream/asbroadcaststream)({void
onListen([StreamSubscription](../dart-async/streamsubscription-class)\<[RawSocketEvent](rawsocketevent-class)\>
subscription)?, void
onCancel([StreamSubscription](../dart-async/streamsubscription-class)\<[RawSocketEvent](rawsocketevent-class)\>
subscription)?}) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](../dart-async/stream/asyncexpand)\<E\>([Stream](../dart-async/stream-class)\<E\>?
convert([RawSocketEvent](rawsocketevent-class) event)) →
[Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Transforms each element into a sequence of asynchronous events.

[asyncMap](../dart-async/stream/asyncmap)\<E\>([FutureOr](../dart-async/futureor-class)\<E\>
convert([RawSocketEvent](rawsocketevent-class) event)) →
[Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Creates a new stream with each data event of this stream asynchronously
mapped to a new event.

[available](rawsocket/available)() → [int](../dart-core/int-class)

::: {.features}
inherited
:::

The number of received and non-read bytes in the socket that can be
read.

[cast](../dart-async/stream/cast)\<R\>() →
[Stream](../dart-async/stream-class)\<R\>

::: {.features}
inherited
:::

Adapt this stream to be a `Stream<R>`.

[close](rawsocket/close)() →
[Future](../dart-async/future-class)\<[RawSocket](rawsocket-class)\>

::: {.features}
inherited
:::

Closes the socket.

[contains](../dart-async/stream/contains)([Object](../dart-core/object-class)?
needle) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Returns whether `needle` occurs in the elements provided by this stream.

[distinct](../dart-async/stream/distinct)(\[[bool](../dart-core/bool-class)
equals([RawSocketEvent](rawsocketevent-class) previous,
[RawSocketEvent](rawsocketevent-class) next)?\]) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Skips data events if they are equal to the previous data event.

[drain](../dart-async/stream/drain)\<E\>(\[E? futureValue\]) →
[Future](../dart-async/future-class)\<E\>

::: {.features}
inherited
:::

Discards all data on this stream, but signals when it is done or an
error occurred.

[elementAt](../dart-async/stream/elementat)([int](../dart-core/int-class)
index) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Returns the value of the `index`th data event of this stream.

[every](../dart-async/stream/every)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts all elements provided by this stream.

[expand](../dart-async/stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert([RawSocketEvent](rawsocketevent-class) element)) →
[Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a sequence of elements.

[firstWhere](../dart-async/stream/firstwhere)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element),
{[RawSocketEvent](rawsocketevent-class) orElse()?}) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Finds the first element of this stream matching `test`.

[fold](../dart-async/stream/fold)\<S\>(S initialValue, S combine(S
previous, [RawSocketEvent](rawsocketevent-class) element)) →
[Future](../dart-async/future-class)\<S\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[forEach](../dart-async/stream/foreach)(void
action([RawSocketEvent](rawsocketevent-class) element)) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Executes `action` on each element of this stream.

[getRawOption](rawsocket/getrawoption)([RawSocketOption](rawsocketoption-class)
option) → [Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
\@Since(\"2.2\"), inherited
:::

Reads low level information about the [RawSocket](rawsocket-class).

[handleError](../dart-async/stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Creates a wrapper Stream that intercepts some errors from this stream.

[join](../dart-async/stream/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Combines the string representation of elements into a single string.

[lastWhere](../dart-async/stream/lastwhere)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element),
{[RawSocketEvent](rawsocketevent-class) orElse()?}) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[listen](../dart-async/stream/listen)(void
onData([RawSocketEvent](rawsocketevent-class) event)?,
{[Function](../dart-core/function-class)? onError, void onDone()?,
[bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](../dart-async/streamsubscription-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Adds a subscription to this stream.

[map](../dart-async/stream/map)\<S\>(S
convert([RawSocketEvent](rawsocketevent-class) event)) →
[Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a new stream event.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pipe](../dart-async/stream/pipe)([StreamConsumer](../dart-async/streamconsumer-class)\<[RawSocketEvent](rawsocketevent-class)\>
streamConsumer) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Pipes the events of this stream into `streamConsumer`.

[read](rawsocket/read)(\[[int](../dart-core/int-class)? len\]) →
[Uint8List](../dart-typed_data/uint8list-class)?

::: {.features}
inherited
:::

Read up to `len` bytes from the socket.

[readMessage](rawsocket/readmessage)(\[[int](../dart-core/int-class)?
count\]) → [SocketMessage](socketmessage-class)?

::: {.features}
\@Since(\"2.15\"), inherited
:::

Reads a message containing up to `count` bytes from the socket.

[reduce](../dart-async/stream/reduce)([RawSocketEvent](rawsocketevent-class)
combine([RawSocketEvent](rawsocketevent-class) previous,
[RawSocketEvent](rawsocketevent-class) element)) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[renegotiate](rawsecuresocket/renegotiate){.deprecated}({[bool](../dart-core/bool-class)
useSessionCache = true, [bool](../dart-core/bool-class)
requestClientCertificate = false, [bool](../dart-core/bool-class)
requireClientCertificate = false}) → void

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"Not implemented\")
:::

Does nothing.

[sendMessage](rawsocket/sendmessage)([List](../dart-core/list-class)\<[SocketControlMessage](socketcontrolmessage-class)\>
controlMessages,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\> data,
\[[int](../dart-core/int-class) offset = 0,
[int](../dart-core/int-class)? count\]) → [int](../dart-core/int-class)

::: {.features}
\@Since(\"2.15\"), inherited
:::

Writes socket control messages and data bytes to the socket.

[setOption](rawsocket/setoption)([SocketOption](socketoption-class)
option, [bool](../dart-core/bool-class) enabled) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Customize the [RawSocket](rawsocket-class).

[setRawOption](rawsocket/setrawoption)([RawSocketOption](rawsocketoption-class)
option) → void

::: {.features}
\@Since(\"2.2\"), inherited
:::

Customizes the [RawSocket](rawsocket-class).

[shutdown](rawsocket/shutdown)([SocketDirection](socketdirection-class)
direction) → void

::: {.features}
inherited
:::

Shuts down the socket in the `direction`.

[singleWhere](../dart-async/stream/singlewhere)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element),
{[RawSocketEvent](rawsocketevent-class) orElse()?}) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Finds the single element in this stream matching `test`.

[skip](../dart-async/stream/skip)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Skips the first `count` data events from this stream.

[skipWhile](../dart-async/stream/skipwhile)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element)) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Skip data events from this stream while they are matched by `test`.

[take](../dart-async/stream/take)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Provides at most the first `count` data events of this stream.

[takeWhile](../dart-async/stream/takewhile)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element)) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Forwards data events while `test` is successful.

[timeout](../dart-async/stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void
onTimeout([EventSink](../dart-async/eventsink-class)\<[RawSocketEvent](rawsocketevent-class)\>
sink)?}) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Creates a new stream with the same events as this stream.

[toList](../dart-async/stream/tolist)() →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[RawSocketEvent](rawsocketevent-class)\>\>

::: {.features}
inherited
:::

Collects all elements of this stream in a `List`.

[toSet](../dart-async/stream/toset)() →
[Future](../dart-async/future-class)\<[Set](../dart-core/set-class)\<[RawSocketEvent](rawsocketevent-class)\>\>

::: {.features}
inherited
:::

Collects the data of this stream in a `Set`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transform](../dart-async/stream/transform)\<S\>([StreamTransformer](../dart-async/streamtransformer-class)\<[RawSocketEvent](rawsocketevent-class),
S\> streamTransformer) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Applies `streamTransformer` to this stream.

[where](../dart-async/stream/where)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) event)) →
[Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Creates a new stream from this stream that discards some elements.

[write](rawsocket/write)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, \[[int](../dart-core/int-class) offset = 0,
[int](../dart-core/int-class)? count\]) → [int](../dart-core/int-class)

::: {.features}
inherited
:::

Writes up to `count` bytes of the buffer from `offset` buffer offset to
the socket.

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

[connect](rawsecuresocket/connect)(dynamic host,
[int](../dart-core/int-class) port,
{[SecurityContext](securitycontext-class)? context,
[bool](../dart-core/bool-class)
onBadCertificate([X509Certificate](x509certificate-class) certificate)?,
void keyLog([String](../dart-core/string-class) line)?,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?
supportedProtocols, [Duration](../dart-core/duration-class)? timeout}) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
override
:::

Constructs a new secure client socket and connect it to the given host
on the given port.

[secure](rawsecuresocket/secure)([RawSocket](rawsocket-class) socket,
{[StreamSubscription](../dart-async/streamsubscription-class)\<[RawSocketEvent](rawsocketevent-class)\>?
subscription, dynamic host, [SecurityContext](securitycontext-class)?
context, [bool](../dart-core/bool-class)
onBadCertificate([X509Certificate](x509certificate-class) certificate)?,
void keyLog([String](../dart-core/string-class) line)?,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?
supportedProtocols}) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

Initiates TLS on an existing connection.

[secureServer](rawsecuresocket/secureserver)([RawSocket](rawsocket-class)
socket, [SecurityContext](securitycontext-class)? context,
{[StreamSubscription](../dart-async/streamsubscription-class)\<[RawSocketEvent](rawsocketevent-class)\>?
subscription,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?
bufferedData, [bool](../dart-core/bool-class) requestClientCertificate =
false, [bool](../dart-core/bool-class) requireClientCertificate = false,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?
supportedProtocols}) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

Initiates TLS on an existing server connection.

[startConnect](rawsecuresocket/startconnect)(dynamic host,
[int](../dart-core/int-class) port,
{[SecurityContext](securitycontext-class)? context,
[bool](../dart-core/bool-class)
onBadCertificate([X509Certificate](x509certificate-class) certificate)?,
void keyLog([String](../dart-core/string-class) line)?,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?
supportedProtocols}) →
[Future](../dart-async/future-class)\<[ConnectionTask](connectiontask-class)\<[RawSecureSocket](rawsecuresocket-class)\>\>

::: {.features}
override
:::

Like [connect](rawsecuresocket/connect), but returns a
[Future](../dart-async/future-class) that completes with a
`ConnectionTask` that can be cancelled if the
[RawSecureSocket](rawsecuresocket-class) is no longer needed.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSecureSocket-class.html>
:::
