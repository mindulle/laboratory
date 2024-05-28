[dart:io](../dart-io/dart-io-library){._links-link}

Socket class
============

A TCP connection between two sockets.

A *socket connection* connects a *local* socket to a *remote* socket.
Data, as [Uint8List](../dart-typed_data/uint8list-class)s, is received
by the local socket, made available by the
[Stream](../dart-async/stream-class) interface of this class, and can be
sent to the remote socket through the [IOSink](iosink-class) interface
of this class.

Implemented types

:   -   [Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>
    -   [IOSink](iosink-class)

Implementers

:   -   [SecureSocket](securesocket-class)

Constructors
------------

[Socket](socket/socket)()

Properties {#instance-properties}
----------

[address](socket/address) → [InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

The [InternetAddress](internetaddress-class) used to connect this
socket.

[done](socket/done) → [Future](../dart-async/future-class)

::: {.features}
read-only, override
:::

A future that will complete when the consumer closes, or when an error
occurs.

[encoding](iosink/encoding) ↔ [Encoding](../dart-convert/encoding-class)

::: {.features}
read / write, inherited
:::

The [Encoding](../dart-convert/encoding-class) used when writing
strings.

[first](../dart-async/stream/first) →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

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
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

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

[port](socket/port) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The port used by this socket.

[remoteAddress](socket/remoteaddress) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

The remote [InternetAddress](internetaddress-class) connected to by this
socket.

[remotePort](socket/remoteport) → [int](../dart-core/int-class)

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

[single](../dart-async/stream/single) →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
read-only, inherited
:::

The single element of this stream.

Methods {#instance-methods}
-------

[add](iosink/add)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
data) → void

::: {.features}
inherited
:::

Adds byte `data` to the target consumer, ignoring
[encoding](iosink/encoding).

[addError](iosink/adderror)([Object](../dart-core/object-class) error,
\[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) → void

::: {.features}
inherited
:::

Passes the error to the target consumer as an error event.

[addStream](iosink/addstream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
stream) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Adds all elements of the given `stream`.

[any](../dart-async/stream/any)([bool](../dart-core/bool-class)
test([Uint8List](../dart-typed_data/uint8list-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](../dart-async/stream/asbroadcaststream)({void
onListen([StreamSubscription](../dart-async/streamsubscription-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>
subscription)?, void
onCancel([StreamSubscription](../dart-async/streamsubscription-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>
subscription)?}) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](../dart-async/stream/asyncexpand)\<E\>([Stream](../dart-async/stream-class)\<E\>?
convert([Uint8List](../dart-typed_data/uint8list-class) event)) →
[Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Transforms each element into a sequence of asynchronous events.

[asyncMap](../dart-async/stream/asyncmap)\<E\>([FutureOr](../dart-async/futureor-class)\<E\>
convert([Uint8List](../dart-typed_data/uint8list-class) event)) →
[Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Creates a new stream with each data event of this stream asynchronously
mapped to a new event.

[cast](../dart-async/stream/cast)\<R\>() →
[Stream](../dart-async/stream-class)\<R\>

::: {.features}
inherited
:::

Adapt this stream to be a `Stream<R>`.

[close](socket/close)() → [Future](../dart-async/future-class)

::: {.features}
override
:::

Close the target consumer.

[contains](../dart-async/stream/contains)([Object](../dart-core/object-class)?
needle) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Returns whether `needle` occurs in the elements provided by this stream.

[destroy](socket/destroy)() → void

Destroys the socket in both directions.

[distinct](../dart-async/stream/distinct)(\[[bool](../dart-core/bool-class)
equals([Uint8List](../dart-typed_data/uint8list-class) previous,
[Uint8List](../dart-typed_data/uint8list-class) next)?\]) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

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
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Returns the value of the `index`th data event of this stream.

[every](../dart-async/stream/every)([bool](../dart-core/bool-class)
test([Uint8List](../dart-typed_data/uint8list-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts all elements provided by this stream.

[expand](../dart-async/stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert([Uint8List](../dart-typed_data/uint8list-class) element)) →
[Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a sequence of elements.

[firstWhere](../dart-async/stream/firstwhere)([bool](../dart-core/bool-class)
test([Uint8List](../dart-typed_data/uint8list-class) element),
{[Uint8List](../dart-typed_data/uint8list-class) orElse()?}) →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Finds the first element of this stream matching `test`.

[flush](iosink/flush)() → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Returns a [Future](../dart-async/future-class) that completes once all
buffered data is accepted by the underlying
[StreamConsumer](../dart-async/streamconsumer-class).

[fold](../dart-async/stream/fold)\<S\>(S initialValue, S combine(S
previous, [Uint8List](../dart-typed_data/uint8list-class) element)) →
[Future](../dart-async/future-class)\<S\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[forEach](../dart-async/stream/foreach)(void
action([Uint8List](../dart-typed_data/uint8list-class) element)) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Executes `action` on each element of this stream.

[getRawOption](socket/getrawoption)([RawSocketOption](rawsocketoption-class)
option) → [Uint8List](../dart-typed_data/uint8list-class)

Reads low level information about the [RawSocket](rawsocket-class).

[handleError](../dart-async/stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

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
test([Uint8List](../dart-typed_data/uint8list-class) element),
{[Uint8List](../dart-typed_data/uint8list-class) orElse()?}) →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[listen](../dart-async/stream/listen)(void
onData([Uint8List](../dart-typed_data/uint8list-class) event)?,
{[Function](../dart-core/function-class)? onError, void onDone()?,
[bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](../dart-async/streamsubscription-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Adds a subscription to this stream.

[map](../dart-async/stream/map)\<S\>(S
convert([Uint8List](../dart-typed_data/uint8list-class) event)) →
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

[pipe](../dart-async/stream/pipe)([StreamConsumer](../dart-async/streamconsumer-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>
streamConsumer) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Pipes the events of this stream into `streamConsumer`.

[reduce](../dart-async/stream/reduce)([Uint8List](../dart-typed_data/uint8list-class)
combine([Uint8List](../dart-typed_data/uint8list-class) previous,
[Uint8List](../dart-typed_data/uint8list-class) element)) →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[setOption](socket/setoption)([SocketOption](socketoption-class) option,
[bool](../dart-core/bool-class) enabled) →
[bool](../dart-core/bool-class)

Customizes the [RawSocket](rawsocket-class).

[setRawOption](socket/setrawoption)([RawSocketOption](rawsocketoption-class)
option) → void

Customizes the [RawSocket](rawsocket-class).

[singleWhere](../dart-async/stream/singlewhere)([bool](../dart-core/bool-class)
test([Uint8List](../dart-typed_data/uint8list-class) element),
{[Uint8List](../dart-typed_data/uint8list-class) orElse()?}) →
[Future](../dart-async/future-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Finds the single element in this stream matching `test`.

[skip](../dart-async/stream/skip)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Skips the first `count` data events from this stream.

[skipWhile](../dart-async/stream/skipwhile)([bool](../dart-core/bool-class)
test([Uint8List](../dart-typed_data/uint8list-class) element)) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Skip data events from this stream while they are matched by `test`.

[take](../dart-async/stream/take)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Provides at most the first `count` data events of this stream.

[takeWhile](../dart-async/stream/takewhile)([bool](../dart-core/bool-class)
test([Uint8List](../dart-typed_data/uint8list-class) element)) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Forwards data events while `test` is successful.

[timeout](../dart-async/stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void
onTimeout([EventSink](../dart-async/eventsink-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>
sink)?}) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Creates a new stream with the same events as this stream.

[toList](../dart-async/stream/tolist)() →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>\>

::: {.features}
inherited
:::

Collects all elements of this stream in a `List`.

[toSet](../dart-async/stream/toset)() →
[Future](../dart-async/future-class)\<[Set](../dart-core/set-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>\>

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

[transform](../dart-async/stream/transform)\<S\>([StreamTransformer](../dart-async/streamtransformer-class)\<[Uint8List](../dart-typed_data/uint8list-class),
S\> streamTransformer) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Applies `streamTransformer` to this stream.

[where](../dart-async/stream/where)([bool](../dart-core/bool-class)
test([Uint8List](../dart-typed_data/uint8list-class) event)) →
[Stream](../dart-async/stream-class)\<[Uint8List](../dart-typed_data/uint8list-class)\>

::: {.features}
inherited
:::

Creates a new stream from this stream that discards some elements.

[write](iosink/write)([Object](../dart-core/object-class)? object) →
void

::: {.features}
inherited
:::

Converts `object` to a String by invoking
[Object.toString](../dart-core/object/tostring) and [add](iosink/add)s
the encoding of the result to the target consumer.

[writeAll](iosink/writeall)([Iterable](../dart-core/iterable-class)
objects, \[[String](../dart-core/string-class) separator = \"\"\]) →
void

::: {.features}
inherited
:::

Iterates over the given `objects` and [write](iosink/write)s them in
sequence.

[writeCharCode](iosink/writecharcode)([int](../dart-core/int-class)
charCode) → void

::: {.features}
inherited
:::

Writes the character of `charCode`.

[writeln](iosink/writeln)(\[[Object](../dart-core/object-class)? object
= \"\"\]) → void

::: {.features}
inherited
:::

Converts `object` to a String by invoking
[Object.toString](../dart-core/object/tostring) and writes the result to
`this`, followed by a newline.

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

[connect](socket/connect)(dynamic host, [int](../dart-core/int-class) port, {dynamic sourceAddress, [int](../dart-core/int-class) sourcePort = 0, [Duration](../dart-core/duration-class)? timeout}) → [Future](../dart-async/future-class)\<[Socket](socket-class)\>
:   Creates a new socket connection to the host and port and returns a
    [Future](../dart-async/future-class) that will complete with either
    a `Socket` once connected or an error if the host-lookup or
    connection failed.

[startConnect](socket/startconnect)(dynamic host, [int](../dart-core/int-class) port, {dynamic sourceAddress, [int](../dart-core/int-class) sourcePort = 0}) → [Future](../dart-async/future-class)\<[ConnectionTask](connectiontask-class)\<[Socket](socket-class)\>\>
:   Like [connect](socket/connect), but returns a
    [Future](../dart-async/future-class) that completes with a
    `ConnectionTask` that can be cancelled if the [Socket](socket-class)
    is no longer needed.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket-class.html>
:::
