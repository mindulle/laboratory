[dart:io](../dart-io/dart-io-library){._links-link}

RawDatagramSocket class
=======================

An unbuffered interface to a UDP socket.

The raw datagram socket delivers the datagrams in the same chunks as the
underlying operating system. It\'s a
[Stream](../dart-async/stream-class) of
[RawSocketEvent](rawsocketevent-class)s.

Note that the event
[RawSocketEvent.readClosed](rawsocketevent/readclosed-constant) will
never be received as an UDP socket cannot be closed by a remote peer.

It is not the same as a [POSIX raw
socket](http://man7.org/linux/man-pages/man7/raw.7.html).

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Stream](../dart-async/stream-class)\<[RawSocketEvent](rawsocketevent-class)\>
    -   RawDatagramSocket

Constructors
------------

[RawDatagramSocket](rawdatagramsocket/rawdatagramsocket)()

Properties {#instance-properties}
----------

[address](rawdatagramsocket/address) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

The address used by this socket.

[broadcastEnabled](rawdatagramsocket/broadcastenabled) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether IPv4 broadcast is enabled.

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

[multicastHops](rawdatagramsocket/multicasthops) ↔
[int](../dart-core/int-class)

::: {.features}
read / write
:::

The maximum network hops for multicast packages originating from this
socket.

[multicastInterface](rawdatagramsocket/multicastinterface){.deprecated}
↔ [NetworkInterface](networkinterface-class)?

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\"This property is not
implemented. Use getRawOption and \" \"setRawOption instead.\"), read /
write
:::

The network interface used for outgoing multicast packages.

[multicastLoopback](rawdatagramsocket/multicastloopback) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether multicast traffic is looped back to the host.

[port](rawdatagramsocket/port) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The port used by this socket.

[readEventsEnabled](rawdatagramsocket/readeventsenabled) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether the [RawDatagramSocket](rawdatagramsocket-class) should listen
for [RawSocketEvent.read](rawsocketevent/read-constant) events.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](../dart-async/stream/single) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
read-only, inherited
:::

The single element of this stream.

[writeEventsEnabled](rawdatagramsocket/writeeventsenabled) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether the [RawDatagramSocket](rawdatagramsocket-class) should listen
for [RawSocketEvent.write](rawsocketevent/write-constant) events.

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

[cast](../dart-async/stream/cast)\<R\>() →
[Stream](../dart-async/stream-class)\<R\>

::: {.features}
inherited
:::

Adapt this stream to be a `Stream<R>`.

[close](rawdatagramsocket/close)() → void

Closes the datagram socket.

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

[getRawOption](rawdatagramsocket/getrawoption)([RawSocketOption](rawsocketoption-class)
option) → [Uint8List](../dart-typed_data/uint8list-class)

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

[joinMulticast](rawdatagramsocket/joinmulticast)([InternetAddress](internetaddress-class)
group, \[[NetworkInterface](networkinterface-class)? interface\]) → void

Joins a multicast group.

[lastWhere](../dart-async/stream/lastwhere)([bool](../dart-core/bool-class)
test([RawSocketEvent](rawsocketevent-class) element),
{[RawSocketEvent](rawsocketevent-class) orElse()?}) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[leaveMulticast](rawdatagramsocket/leavemulticast)([InternetAddress](internetaddress-class)
group, \[[NetworkInterface](networkinterface-class)? interface\]) → void

Leaves a multicast group.

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

[receive](rawdatagramsocket/receive)() → [Datagram](datagram-class)?

Receives a datagram.

[reduce](../dart-async/stream/reduce)([RawSocketEvent](rawsocketevent-class)
combine([RawSocketEvent](rawsocketevent-class) previous,
[RawSocketEvent](rawsocketevent-class) element)) →
[Future](../dart-async/future-class)\<[RawSocketEvent](rawsocketevent-class)\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[send](rawdatagramsocket/send)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
buffer, [InternetAddress](internetaddress-class) address,
[int](../dart-core/int-class) port) → [int](../dart-core/int-class)

Sends a datagram.

[setRawOption](rawdatagramsocket/setrawoption)([RawSocketOption](rawsocketoption-class)
option) → void

Customizes the [RawSocket](rawsocket-class).

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

[bind](rawdatagramsocket/bind)(dynamic host, [int](../dart-core/int-class) port, {[bool](../dart-core/bool-class) reuseAddress = true, [bool](../dart-core/bool-class) reusePort = false, [int](../dart-core/int-class) ttl = 1}) → [Future](../dart-async/future-class)\<[RawDatagramSocket](rawdatagramsocket-class)\>
:   Binds a socket to the given `host` and `port`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket-class.html>
:::
