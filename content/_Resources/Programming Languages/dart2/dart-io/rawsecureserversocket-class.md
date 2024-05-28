[dart:io](../dart-io/dart-io-library){._links-link}

RawSecureServerSocket class
===========================

A server socket providing a stream of low-level
[RawSecureSocket](rawsecuresocket-class)s.

See [RawSecureSocket](rawsecuresocket-class) for more info.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>
    -   RawSecureServerSocket

Properties {#instance-properties}
----------

[address](rawsecureserversocket/address) →
[InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

The address used by this socket.

[first](../dart-async/stream/first) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

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
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

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

[port](rawsecureserversocket/port) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The port used by this socket.

[requestClientCertificate](rawsecureserversocket/requestclientcertificate)
→ [bool](../dart-core/bool-class)

::: {.features}
final
:::

[requireClientCertificate](rawsecureserversocket/requireclientcertificate)
→ [bool](../dart-core/bool-class)

::: {.features}
final
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](../dart-async/stream/single) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
read-only, inherited
:::

The single element of this stream.

[supportedProtocols](rawsecureserversocket/supportedprotocols) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

::: {.features}
final
:::

Methods {#instance-methods}
-------

[any](../dart-async/stream/any)([bool](../dart-core/bool-class)
test([RawSecureSocket](rawsecuresocket-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](../dart-async/stream/asbroadcaststream)({void
onListen([StreamSubscription](../dart-async/streamsubscription-class)\<[RawSecureSocket](rawsecuresocket-class)\>
subscription)?, void
onCancel([StreamSubscription](../dart-async/streamsubscription-class)\<[RawSecureSocket](rawsecuresocket-class)\>
subscription)?}) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](../dart-async/stream/asyncexpand)\<E\>([Stream](../dart-async/stream-class)\<E\>?
convert([RawSecureSocket](rawsecuresocket-class) event)) →
[Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Transforms each element into a sequence of asynchronous events.

[asyncMap](../dart-async/stream/asyncmap)\<E\>([FutureOr](../dart-async/futureor-class)\<E\>
convert([RawSecureSocket](rawsecuresocket-class) event)) →
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

[close](rawsecureserversocket/close)() →
[Future](../dart-async/future-class)\<[RawSecureServerSocket](rawsecureserversocket-class)\>

Closes this socket.

[contains](../dart-async/stream/contains)([Object](../dart-core/object-class)?
needle) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Returns whether `needle` occurs in the elements provided by this stream.

[distinct](../dart-async/stream/distinct)(\[[bool](../dart-core/bool-class)
equals([RawSecureSocket](rawsecuresocket-class) previous,
[RawSecureSocket](rawsecuresocket-class) next)?\]) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

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
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Returns the value of the `index`th data event of this stream.

[every](../dart-async/stream/every)([bool](../dart-core/bool-class)
test([RawSecureSocket](rawsecuresocket-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts all elements provided by this stream.

[expand](../dart-async/stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert([RawSecureSocket](rawsecuresocket-class) element)) →
[Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a sequence of elements.

[firstWhere](../dart-async/stream/firstwhere)([bool](../dart-core/bool-class)
test([RawSecureSocket](rawsecuresocket-class) element),
{[RawSecureSocket](rawsecuresocket-class) orElse()?}) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Finds the first element of this stream matching `test`.

[fold](../dart-async/stream/fold)\<S\>(S initialValue, S combine(S
previous, [RawSecureSocket](rawsecuresocket-class) element)) →
[Future](../dart-async/future-class)\<S\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[forEach](../dart-async/stream/foreach)(void
action([RawSecureSocket](rawsecuresocket-class) element)) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Executes `action` on each element of this stream.

[handleError](../dart-async/stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

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
test([RawSecureSocket](rawsecuresocket-class) element),
{[RawSecureSocket](rawsecuresocket-class) orElse()?}) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[listen](rawsecureserversocket/listen)(void
onData([RawSecureSocket](rawsecuresocket-class) s)?,
{[Function](../dart-core/function-class)? onError, void onDone()?,
[bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](../dart-async/streamsubscription-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
override
:::

Adds a subscription to this stream.

[map](../dart-async/stream/map)\<S\>(S
convert([RawSecureSocket](rawsecuresocket-class) event)) →
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

[pipe](../dart-async/stream/pipe)([StreamConsumer](../dart-async/streamconsumer-class)\<[RawSecureSocket](rawsecuresocket-class)\>
streamConsumer) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Pipes the events of this stream into `streamConsumer`.

[reduce](../dart-async/stream/reduce)([RawSecureSocket](rawsecuresocket-class)
combine([RawSecureSocket](rawsecuresocket-class) previous,
[RawSecureSocket](rawsecuresocket-class) element)) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[singleWhere](../dart-async/stream/singlewhere)([bool](../dart-core/bool-class)
test([RawSecureSocket](rawsecuresocket-class) element),
{[RawSecureSocket](rawsecuresocket-class) orElse()?}) →
[Future](../dart-async/future-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Finds the single element in this stream matching `test`.

[skip](../dart-async/stream/skip)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Skips the first `count` data events from this stream.

[skipWhile](../dart-async/stream/skipwhile)([bool](../dart-core/bool-class)
test([RawSecureSocket](rawsecuresocket-class) element)) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Skip data events from this stream while they are matched by `test`.

[take](../dart-async/stream/take)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Provides at most the first `count` data events of this stream.

[takeWhile](../dart-async/stream/takewhile)([bool](../dart-core/bool-class)
test([RawSecureSocket](rawsecuresocket-class) element)) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Forwards data events while `test` is successful.

[timeout](../dart-async/stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void
onTimeout([EventSink](../dart-async/eventsink-class)\<[RawSecureSocket](rawsecuresocket-class)\>
sink)?}) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

::: {.features}
inherited
:::

Creates a new stream with the same events as this stream.

[toList](../dart-async/stream/tolist)() →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[RawSecureSocket](rawsecuresocket-class)\>\>

::: {.features}
inherited
:::

Collects all elements of this stream in a `List`.

[toSet](../dart-async/stream/toset)() →
[Future](../dart-async/future-class)\<[Set](../dart-core/set-class)\<[RawSecureSocket](rawsecuresocket-class)\>\>

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

[transform](../dart-async/stream/transform)\<S\>([StreamTransformer](../dart-async/streamtransformer-class)\<[RawSecureSocket](rawsecuresocket-class),
S\> streamTransformer) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Applies `streamTransformer` to this stream.

[where](../dart-async/stream/where)([bool](../dart-core/bool-class)
test([RawSecureSocket](rawsecuresocket-class) event)) →
[Stream](../dart-async/stream-class)\<[RawSecureSocket](rawsecuresocket-class)\>

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

[bind](rawsecureserversocket/bind)(dynamic address, [int](../dart-core/int-class) port, [SecurityContext](securitycontext-class)? context, {[int](../dart-core/int-class) backlog = 0, [bool](../dart-core/bool-class) v6Only = false, [bool](../dart-core/bool-class) requestClientCertificate = false, [bool](../dart-core/bool-class) requireClientCertificate = false, [List](../dart-core/list-class)\<[String](../dart-core/string-class)\>? supportedProtocols, [bool](../dart-core/bool-class) shared = false}) → [Future](../dart-async/future-class)\<[RawSecureServerSocket](rawsecureserversocket-class)\>
:   Listens on a provided address and port.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSecureServerSocket-class.html>
:::
