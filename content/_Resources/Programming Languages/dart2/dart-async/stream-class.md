[dart:async](../dart-async/dart-async-library){._links-link}

Stream\<T\> class
=================

A source of asynchronous data events.

A Stream provides a way to receive a sequence of events. Each event is
either a data event, also called an *element* of the stream, or an error
event, which is a notification that something has failed. When a stream
has emitted all its events, a single \"done\" event notifies the
listener that the end has been reached.

You produce a stream by calling an `async*` function, which then returns
a stream. Consuming that stream will lead the function to emit events
until it ends, and the stream closes. You consume a stream either using
an `await for` loop, which is available inside an `async` or `async*`
function, or by forwarding its events directly using `yield*` inside an
`async*` function. Example:

``` {.language-dart data-language="dart"}
Stream<T> optionalMap<T>(
    Stream<T> source , [T Function(T)? convert]) async* {
  if (convert == null) {
    yield* source;
  } else {
    await for (var event in source) {
      yield convert(event);
    }
  }
}
```

When this function is called, it immediately returns a `Stream<T>`
object. Then nothing further happens until someone tries to consume that
stream. At that point, the body of the `async*` function starts running.
If the `convert` function was omitted, the `yield*` will listen to the
`source` stream and forward all events, date and errors, to the returned
stream. When the `source` stream closes, the `yield*` is done, and the
`optionalMap` function body ends too. This closes the returned stream.
If a `convert` *is* supplied, the function instead listens on the source
stream and enters an `await for` loop which repeatedly waits for the
next data event. On a data event, it calls `convert` with the value and
emits the result on the returned stream. If no error events are emitted
by the `source` stream, the loop ends when the `source` stream does,
then the `optionalMap` function body completes, which closes the
returned stream. On an error event from the `source` stream, the
`await for` re-throws that error, which breaks the loop. The error then
reaches the end of the `optionalMap` function body, since it\'s not
caught. That makes the error be emitted on the returned stream, which
then closes.

The `Stream` class also provides functionality which allows you to
manually listen for events from a stream, or to convert a stream into
another stream or into a future.

The [forEach](stream/foreach) function corresponds to the `await for`
loop, just as [Iterable.forEach](../dart-core/iterable/foreach)
corresponds to a normal `for`/`in` loop. Like the loop, it will call a
function for each data event and break on an error.

The more low-level [listen](stream/listen) method is what every other
method is based on. You call `listen` on a stream to tell it that you
want to receive events, and to register the callbacks which will receive
those events. When you call `listen`, you receive a
[StreamSubscription](streamsubscription-class) object which is the
active object providing the events, and which can be used to stop
listening again, or to temporarily pause events from the subscription.

There are two kinds of streams: \"Single-subscription\" streams and
\"broadcast\" streams.

*A single-subscription stream* allows only a single listener during the
whole lifetime of the stream. It doesn\'t start generating events until
it has a listener, and it stops sending events when the listener is
unsubscribed, even if the source of events could still provide more. The
stream created by an `async*` function is a single-subscription stream,
but each call to the function creates a new such stream.

Listening twice on a single-subscription stream is not allowed, even
after the first subscription has been canceled.

Single-subscription streams are generally used for streaming chunks of
larger contiguous data, like file I/O.

*A broadcast stream* allows any number of listeners, and it fires its
events when they are ready, whether there are listeners or not.

Broadcast streams are used for independent events/observers.

If several listeners want to listen to a single-subscription stream, use
[asBroadcastStream](stream/asbroadcaststream) to create a broadcast
stream on top of the non-broadcast stream.

On either kind of stream, stream transformations, such as
[where](stream/where) and [skip](stream/skip), return the same type of
stream as the one the method was called on, unless otherwise noted.

When an event is fired, the listener(s) at that time will receive the
event. If a listener is added to a broadcast stream while an event is
being fired, that listener will not receive the event currently being
fired. If a listener is canceled, it immediately stops receiving events.
Listening on a broadcast stream can be treated as listening on a new
stream containing only the events that have not yet been emitted when
the [listen](stream/listen) call occurs. For example the
[first](stream/first) getter listens to the stream, then returns the
first event that listener receives. This is not necessarily the first
even emitted by the stream, but the first of the *remaining* events of
the broadcast stream.

When the \"done\" event is fired, subscribers are unsubscribed before
receiving the event. After the event has been sent, the stream has no
subscribers. Adding new subscribers to a broadcast stream after this
point is allowed, but they will just receive a new \"done\" event as
soon as possible.

Stream subscriptions always respect \"pause\" requests. If necessary
they need to buffer their input, but often, and preferably they can
simply request their input to pause too.

The default implementation of [isBroadcast](stream/isbroadcast) returns
false. A broadcast stream inheriting from [Stream](stream-class) must
override [isBroadcast](stream/isbroadcast) to return `true` if it wants
to signal that it behaves like a broadcast stream.

Implementers

:   -   [CustomStream](../dart-html/customstream-class)
    -   [ElementStream](../dart-html/elementstream-class)
    -   [HttpClientResponse](../dart-io/httpclientresponse-class)
    -   [HttpRequest](../dart-io/httprequest-class)
    -   [HttpServer](../dart-io/httpserver-class)
    -   [RawDatagramSocket](../dart-io/rawdatagramsocket-class)
    -   [RawSecureServerSocket](../dart-io/rawsecureserversocket-class)
    -   [RawServerSocket](../dart-io/rawserversocket-class)
    -   [RawSocket](../dart-io/rawsocket-class)
    -   [ReceivePort](../dart-isolate/receiveport-class)
    -   [SecureServerSocket](../dart-io/secureserversocket-class)
    -   [ServerSocket](../dart-io/serversocket-class)
    -   [Socket](../dart-io/socket-class)
    -   [Stdin](../dart-io/stdin-class)
    -   [StreamView](streamview-class)
    -   [WebSocket](../dart-io/websocket-class)

Constructors
------------

[Stream](stream/stream)()

[Stream.empty](stream/stream.empty)()

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Creates an empty broadcast stream.

[Stream.error](stream/stream.error)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\])

::: {.constructor-modifier .features}
factory
:::

Creates a stream which emits a single error event before completing.

[Stream.eventTransformed](stream/stream.eventtransformed)([Stream](stream-class)
source, [EventSink](eventsink-class)
mapSink([EventSink](eventsink-class)\<T\> sink))

::: {.constructor-modifier .features}
factory
:::

Creates a stream where all events of an existing stream are piped
through a sink-transformation.

[Stream.fromFuture](stream/stream.fromfuture)([Future](future-class)\<T\>
future)

::: {.constructor-modifier .features}
factory
:::

Creates a new single-subscription stream from the future.

[Stream.fromFutures](stream/stream.fromfutures)([Iterable](../dart-core/iterable-class)\<[Future](future-class)\<T\>\>
futures)

::: {.constructor-modifier .features}
factory
:::

Create a single-subscription stream from a group of futures.

[Stream.fromIterable](stream/stream.fromiterable)([Iterable](../dart-core/iterable-class)\<T\>
elements)

::: {.constructor-modifier .features}
factory
:::

Creates a stream that gets its data from `elements`.

[Stream.multi](stream/stream.multi)(void
onListen([MultiStreamController](multistreamcontroller-class)\<T\>),
{[bool](../dart-core/bool-class) isBroadcast = false})

::: {.constructor-modifier .features}
factory
:::

Creates a multi-subscription stream.

[Stream.periodic](stream/stream.periodic)([Duration](../dart-core/duration-class)
period, \[T computation([int](../dart-core/int-class)
computationCount)?\])

::: {.constructor-modifier .features}
factory
:::

Creates a stream that repeatedly emits events at `period` intervals.

[Stream.value](stream/stream.value)(T value)

::: {.constructor-modifier .features}
factory
:::

Creates a stream which emits a single data event before closing.

Properties {#instance-properties}
----------

[first](stream/first) → [Future](future-class)\<T\>

::: {.features}
read-only
:::

The first element of this stream.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isBroadcast](stream/isbroadcast) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether this stream is a broadcast stream.

[isEmpty](stream/isempty) →
[Future](future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
read-only
:::

Whether this stream contains any elements.

[last](stream/last) → [Future](future-class)\<T\>

::: {.features}
read-only
:::

The last element of this stream.

[length](stream/length) →
[Future](future-class)\<[int](../dart-core/int-class)\>

::: {.features}
read-only
:::

The number of elements in this stream.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](stream/single) → [Future](future-class)\<T\>

::: {.features}
read-only
:::

The single element of this stream.

Methods {#instance-methods}
-------

[any](stream/any)([bool](../dart-core/bool-class) test(T element)) →
[Future](future-class)\<[bool](../dart-core/bool-class)\>

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](stream/asbroadcaststream)({void
onListen([StreamSubscription](streamsubscription-class)\<T\>
subscription)?, void
onCancel([StreamSubscription](streamsubscription-class)\<T\>
subscription)?}) → [Stream](stream-class)\<T\>

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](stream/asyncexpand)\<E\>([Stream](stream-class)\<E\>?
convert(T event)) → [Stream](stream-class)\<E\>

Transforms each element into a sequence of asynchronous events.

[asyncMap](stream/asyncmap)\<E\>([FutureOr](futureor-class)\<E\>
convert(T event)) → [Stream](stream-class)\<E\>

Creates a new stream with each data event of this stream asynchronously
mapped to a new event.

[cast](stream/cast)\<R\>() → [Stream](stream-class)\<R\>

Adapt this stream to be a `Stream<R>`.

[contains](stream/contains)([Object](../dart-core/object-class)? needle)
→ [Future](future-class)\<[bool](../dart-core/bool-class)\>

Returns whether `needle` occurs in the elements provided by this stream.

[distinct](stream/distinct)(\[[bool](../dart-core/bool-class) equals(T
previous, T next)?\]) → [Stream](stream-class)\<T\>

Skips data events if they are equal to the previous data event.

[drain](stream/drain)\<E\>(\[E? futureValue\]) →
[Future](future-class)\<E\>

Discards all data on this stream, but signals when it is done or an
error occurred.

[elementAt](stream/elementat)([int](../dart-core/int-class) index) →
[Future](future-class)\<T\>

Returns the value of the `index`th data event of this stream.

[every](stream/every)([bool](../dart-core/bool-class) test(T element)) →
[Future](future-class)\<[bool](../dart-core/bool-class)\>

Checks whether `test` accepts all elements provided by this stream.

[expand](stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert(T element)) → [Stream](stream-class)\<S\>

Transforms each element of this stream into a sequence of elements.

[firstWhere](stream/firstwhere)([bool](../dart-core/bool-class) test(T
element), {T orElse()?}) → [Future](future-class)\<T\>

Finds the first element of this stream matching `test`.

[fold](stream/fold)\<S\>(S initialValue, S combine(S previous, T
element)) → [Future](future-class)\<S\>

Combines a sequence of values by repeatedly applying `combine`.

[forEach](stream/foreach)(void action(T element)) →
[Future](future-class)

Executes `action` on each element of this stream.

[handleError](stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](stream-class)\<T\>

Creates a wrapper Stream that intercepts some errors from this stream.

[join](stream/join)(\[[String](../dart-core/string-class) separator =
\"\"\]) → [Future](future-class)\<[String](../dart-core/string-class)\>

Combines the string representation of elements into a single string.

[lastWhere](stream/lastwhere)([bool](../dart-core/bool-class) test(T
element), {T orElse()?}) → [Future](future-class)\<T\>

Finds the last element in this stream matching `test`.

[listen](stream/listen)(void onData(T event)?,
{[Function](../dart-core/function-class)? onError, void onDone()?,
[bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](streamsubscription-class)\<T\>

Adds a subscription to this stream.

[map](stream/map)\<S\>(S convert(T event)) → [Stream](stream-class)\<S\>

Transforms each element of this stream into a new stream event.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pipe](stream/pipe)([StreamConsumer](streamconsumer-class)\<T\>
streamConsumer) → [Future](future-class)

Pipes the events of this stream into `streamConsumer`.

[reduce](stream/reduce)(T combine(T previous, T element)) →
[Future](future-class)\<T\>

Combines a sequence of values by repeatedly applying `combine`.

[singleWhere](stream/singlewhere)([bool](../dart-core/bool-class) test(T
element), {T orElse()?}) → [Future](future-class)\<T\>

Finds the single element in this stream matching `test`.

[skip](stream/skip)([int](../dart-core/int-class) count) →
[Stream](stream-class)\<T\>

Skips the first `count` data events from this stream.

[skipWhile](stream/skipwhile)([bool](../dart-core/bool-class) test(T
element)) → [Stream](stream-class)\<T\>

Skip data events from this stream while they are matched by `test`.

[take](stream/take)([int](../dart-core/int-class) count) →
[Stream](stream-class)\<T\>

Provides at most the first `count` data events of this stream.

[takeWhile](stream/takewhile)([bool](../dart-core/bool-class) test(T
element)) → [Stream](stream-class)\<T\>

Forwards data events while `test` is successful.

[timeout](stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void onTimeout([EventSink](eventsink-class)\<T\> sink)?}) →
[Stream](stream-class)\<T\>

Creates a new stream with the same events as this stream.

[toList](stream/tolist)() →
[Future](future-class)\<[List](../dart-core/list-class)\<T\>\>

Collects all elements of this stream in a `List`.

[toSet](stream/toset)() →
[Future](future-class)\<[Set](../dart-core/set-class)\<T\>\>

Collects the data of this stream in a `Set`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transform](stream/transform)\<S\>([StreamTransformer](streamtransformer-class)\<T,
S\> streamTransformer) → [Stream](stream-class)\<S\>

Applies `streamTransformer` to this stream.

[where](stream/where)([bool](../dart-core/bool-class) test(T event)) →
[Stream](stream-class)\<T\>

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

[castFrom](stream/castfrom)\<S, T\>([Stream](stream-class)\<S\> source) → [Stream](stream-class)\<T\>
:   Adapts `source` to be a `Stream<T>`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream-class.html>
:::
