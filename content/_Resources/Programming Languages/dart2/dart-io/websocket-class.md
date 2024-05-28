[dart:io](../dart-io/dart-io-library){._links-link}

WebSocket class
===============

A two-way HTTP communication object for client or server applications.

The stream exposes the messages received. A text message will be of type
`String` and a binary message will be of type `List<int>`.

Implemented types

:   -   [Stream](../dart-async/stream-class)
    -   [StreamSink](../dart-async/streamsink-class)

Constructors
------------

[WebSocket](websocket/websocket){.deprecated}()

[WebSocket.fromUpgradedSocket](websocket/websocket.fromupgradedsocket)([Socket](socket-class)
socket, {[String](../dart-core/string-class)? protocol,
[bool](../dart-core/bool-class)? serverSide,
[CompressionOptions](compressionoptions-class) compression =
CompressionOptions.compressionDefault})

::: {.constructor-modifier .features}
factory
:::

Creates a WebSocket from an already-upgraded socket.

Properties {#instance-properties}
----------

[closeCode](websocket/closecode) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

The close code set when the WebSocket connection is closed. If there is
no close code available this property will be `null`

[closeReason](websocket/closereason) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

The close reason set when the WebSocket connection is closed. If there
is no close reason available this property will be `null`

[done](../dart-async/streamsink/done) →
[Future](../dart-async/future-class)

::: {.features}
read-only, inherited
:::

Return a future which is completed when the
[StreamSink](../dart-async/streamsink-class) is finished.

[extensions](websocket/extensions) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The extensions property is initially the empty string. After the
WebSocket connection is established this string reflects the extensions
used by the server.

[first](../dart-async/stream/first) →
[Future](../dart-async/future-class)

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

[last](../dart-async/stream/last) → [Future](../dart-async/future-class)

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

[pingInterval](websocket/pinginterval) ↔
[Duration](../dart-core/duration-class)?

::: {.features}
read / write
:::

The interval between ping signals.

[protocol](websocket/protocol) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

The protocol property is initially the empty string. After the WebSocket
connection is established the value is the subprotocol selected by the
server. If no subprotocol is negotiated the value will remain `null`.

[readyState](websocket/readystate) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Returns the current state of the connection.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](../dart-async/stream/single) →
[Future](../dart-async/future-class)

::: {.features}
read-only, inherited
:::

The single element of this stream.

Methods {#instance-methods}
-------

[add](websocket/add)(dynamic data) → void

::: {.features}
override
:::

Sends data on the WebSocket connection. The data in `data` must be
either a `String`, or a `List<int>` holding bytes.

[addError](../dart-async/eventsink/adderror)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

::: {.features}
inherited
:::

Adds an `error` to the sink.

[addStream](websocket/addstream)([Stream](../dart-async/stream-class)
stream) → [Future](../dart-async/future-class)

::: {.features}
override
:::

Sends data from a stream on WebSocket connection. Each data event from
`stream` will be send as a single WebSocket frame. The data from
`stream` must be either `String`s, or `List<int>`s holding bytes.

[addUtf8Text](websocket/addutf8text)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes) → void

Sends a text message with the text represented by `bytes`.

[any](../dart-async/stream/any)([bool](../dart-core/bool-class)
test(dynamic element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](../dart-async/stream/asbroadcaststream)({void
onListen([StreamSubscription](../dart-async/streamsubscription-class)
subscription)?, void
onCancel([StreamSubscription](../dart-async/streamsubscription-class)
subscription)?}) → [Stream](../dart-async/stream-class)

::: {.features}
inherited
:::

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](../dart-async/stream/asyncexpand)\<E\>([Stream](../dart-async/stream-class)\<E\>?
convert(dynamic event)) → [Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Transforms each element into a sequence of asynchronous events.

[asyncMap](../dart-async/stream/asyncmap)\<E\>([FutureOr](../dart-async/futureor-class)\<E\>
convert(dynamic event)) → [Stream](../dart-async/stream-class)\<E\>

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

[close](websocket/close)(\[[int](../dart-core/int-class)? code,
[String](../dart-core/string-class)? reason\]) →
[Future](../dart-async/future-class)

::: {.features}
override
:::

Closes the WebSocket connection. Set the optional `code` and `reason`
arguments to send close information to the remote peer. If they are
omitted, the peer will see
[WebSocketStatus.noStatusReceived](websocketstatus/nostatusreceived-constant)
code with no reason.

[contains](../dart-async/stream/contains)([Object](../dart-core/object-class)?
needle) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Returns whether `needle` occurs in the elements provided by this stream.

[distinct](../dart-async/stream/distinct)(\[[bool](../dart-core/bool-class)
equals(dynamic previous, dynamic next)?\]) →
[Stream](../dart-async/stream-class)

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
index) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Returns the value of the `index`th data event of this stream.

[every](../dart-async/stream/every)([bool](../dart-core/bool-class)
test(dynamic element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts all elements provided by this stream.

[expand](../dart-async/stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert(dynamic element)) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a sequence of elements.

[firstWhere](../dart-async/stream/firstwhere)([bool](../dart-core/bool-class)
test(dynamic element), {dynamic orElse()?}) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Finds the first element of this stream matching `test`.

[fold](../dart-async/stream/fold)\<S\>(S initialValue, S combine(S
previous, dynamic element)) → [Future](../dart-async/future-class)\<S\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[forEach](../dart-async/stream/foreach)(void action(dynamic element)) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Executes `action` on each element of this stream.

[handleError](../dart-async/stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](../dart-async/stream-class)

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
test(dynamic element), {dynamic orElse()?}) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[listen](../dart-async/stream/listen)(void onData(dynamic event)?,
{[Function](../dart-core/function-class)? onError, void onDone()?,
[bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](../dart-async/streamsubscription-class)

::: {.features}
inherited
:::

Adds a subscription to this stream.

[map](../dart-async/stream/map)\<S\>(S convert(dynamic event)) →
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

[pipe](../dart-async/stream/pipe)([StreamConsumer](../dart-async/streamconsumer-class)
streamConsumer) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Pipes the events of this stream into `streamConsumer`.

[reduce](../dart-async/stream/reduce)(dynamic combine(dynamic previous,
dynamic element)) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[singleWhere](../dart-async/stream/singlewhere)([bool](../dart-core/bool-class)
test(dynamic element), {dynamic orElse()?}) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Finds the single element in this stream matching `test`.

[skip](../dart-async/stream/skip)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)

::: {.features}
inherited
:::

Skips the first `count` data events from this stream.

[skipWhile](../dart-async/stream/skipwhile)([bool](../dart-core/bool-class)
test(dynamic element)) → [Stream](../dart-async/stream-class)

::: {.features}
inherited
:::

Skip data events from this stream while they are matched by `test`.

[take](../dart-async/stream/take)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)

::: {.features}
inherited
:::

Provides at most the first `count` data events of this stream.

[takeWhile](../dart-async/stream/takewhile)([bool](../dart-core/bool-class)
test(dynamic element)) → [Stream](../dart-async/stream-class)

::: {.features}
inherited
:::

Forwards data events while `test` is successful.

[timeout](../dart-async/stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void onTimeout([EventSink](../dart-async/eventsink-class)
sink)?}) → [Stream](../dart-async/stream-class)

::: {.features}
inherited
:::

Creates a new stream with the same events as this stream.

[toList](../dart-async/stream/tolist)() →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\>

::: {.features}
inherited
:::

Collects all elements of this stream in a `List`.

[toSet](../dart-async/stream/toset)() →
[Future](../dart-async/future-class)\<[Set](../dart-core/set-class)\>

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

[transform](../dart-async/stream/transform)\<S\>([StreamTransformer](../dart-async/streamtransformer-class)\<dynamic,
S\> streamTransformer) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Applies `streamTransformer` to this stream.

[where](../dart-async/stream/where)([bool](../dart-core/bool-class)
test(dynamic event)) → [Stream](../dart-async/stream-class)

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

Static Properties
-----------------

[userAgent](websocket/useragent) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

Gets the user agent used for WebSocket connections.

Static Methods
--------------

[connect](websocket/connect)([String](../dart-core/string-class) url, {[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>? protocols, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), dynamic\>? headers, [CompressionOptions](compressionoptions-class) compression = CompressionOptions.compressionDefault, [HttpClient](httpclient-class)? customClient}) → [Future](../dart-async/future-class)\<[WebSocket](websocket-class)\>
:   Create a new WebSocket connection. The URL supplied in `url` must
    use the scheme `ws` or `wss`.

Constants
---------

[closed](websocket/closed-constant) → const [int](../dart-core/int-class)

:   <div>

    `3`

    </div>

[closing](websocket/closing-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[connecting](websocket/connecting-constant) → const [int](../dart-core/int-class)
:   Possible states of the connection.
    <div>

    `0`

    </div>

[open](websocket/open-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket-class.html>
:::
