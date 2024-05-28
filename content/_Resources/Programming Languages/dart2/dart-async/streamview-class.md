[dart:async](../dart-async/dart-async-library){._links-link}

StreamView\<T\> class
=====================

[Stream](stream-class) wrapper that only exposes the
[Stream](stream-class) interface.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Stream](stream-class)\<T\>
    -   StreamView

Constructors
------------

[StreamView](streamview/streamview)([Stream](stream-class)\<T\> stream)

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[first](stream/first) → [Future](future-class)\<T\>

::: {.features}
read-only, inherited
:::

The first element of this stream.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isBroadcast](streamview/isbroadcast) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this stream is a broadcast stream.

[isEmpty](stream/isempty) →
[Future](future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
read-only, inherited
:::

Whether this stream contains any elements.

[last](stream/last) → [Future](future-class)\<T\>

::: {.features}
read-only, inherited
:::

The last element of this stream.

[length](stream/length) →
[Future](future-class)\<[int](../dart-core/int-class)\>

::: {.features}
read-only, inherited
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
read-only, inherited
:::

The single element of this stream.

Methods {#instance-methods}
-------

[any](stream/any)([bool](../dart-core/bool-class) test(T element)) →
[Future](future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](streamview/asbroadcaststream)({void
onListen([StreamSubscription](streamsubscription-class)\<T\>
subscription)?, void
onCancel([StreamSubscription](streamsubscription-class)\<T\>
subscription)?}) → [Stream](stream-class)\<T\>

::: {.features}
override
:::

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](stream/asyncexpand)\<E\>([Stream](stream-class)\<E\>?
convert(T event)) → [Stream](stream-class)\<E\>

::: {.features}
inherited
:::

Transforms each element into a sequence of asynchronous events.

[asyncMap](stream/asyncmap)\<E\>([FutureOr](futureor-class)\<E\>
convert(T event)) → [Stream](stream-class)\<E\>

::: {.features}
inherited
:::

Creates a new stream with each data event of this stream asynchronously
mapped to a new event.

[cast](stream/cast)\<R\>() → [Stream](stream-class)\<R\>

::: {.features}
inherited
:::

Adapt this stream to be a `Stream<R>`.

[contains](stream/contains)([Object](../dart-core/object-class)? needle)
→ [Future](future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Returns whether `needle` occurs in the elements provided by this stream.

[distinct](stream/distinct)(\[[bool](../dart-core/bool-class) equals(T
previous, T next)?\]) → [Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Skips data events if they are equal to the previous data event.

[drain](stream/drain)\<E\>(\[E? futureValue\]) →
[Future](future-class)\<E\>

::: {.features}
inherited
:::

Discards all data on this stream, but signals when it is done or an
error occurred.

[elementAt](stream/elementat)([int](../dart-core/int-class) index) →
[Future](future-class)\<T\>

::: {.features}
inherited
:::

Returns the value of the `index`th data event of this stream.

[every](stream/every)([bool](../dart-core/bool-class) test(T element)) →
[Future](future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts all elements provided by this stream.

[expand](stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert(T element)) → [Stream](stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a sequence of elements.

[firstWhere](stream/firstwhere)([bool](../dart-core/bool-class) test(T
element), {T orElse()?}) → [Future](future-class)\<T\>

::: {.features}
inherited
:::

Finds the first element of this stream matching `test`.

[fold](stream/fold)\<S\>(S initialValue, S combine(S previous, T
element)) → [Future](future-class)\<S\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[forEach](stream/foreach)(void action(T element)) →
[Future](future-class)

::: {.features}
inherited
:::

Executes `action` on each element of this stream.

[handleError](stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Creates a wrapper Stream that intercepts some errors from this stream.

[join](stream/join)(\[[String](../dart-core/string-class) separator =
\"\"\]) → [Future](future-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Combines the string representation of elements into a single string.

[lastWhere](stream/lastwhere)([bool](../dart-core/bool-class) test(T
element), {T orElse()?}) → [Future](future-class)\<T\>

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[listen](streamview/listen)(void onData(T value)?,
{[Function](../dart-core/function-class)? onError, void onDone()?,
[bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](streamsubscription-class)\<T\>

::: {.features}
override
:::

Adds a subscription to this stream.

[map](stream/map)\<S\>(S convert(T event)) → [Stream](stream-class)\<S\>

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

[pipe](stream/pipe)([StreamConsumer](streamconsumer-class)\<T\>
streamConsumer) → [Future](future-class)

::: {.features}
inherited
:::

Pipes the events of this stream into `streamConsumer`.

[reduce](stream/reduce)(T combine(T previous, T element)) →
[Future](future-class)\<T\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[singleWhere](stream/singlewhere)([bool](../dart-core/bool-class) test(T
element), {T orElse()?}) → [Future](future-class)\<T\>

::: {.features}
inherited
:::

Finds the single element in this stream matching `test`.

[skip](stream/skip)([int](../dart-core/int-class) count) →
[Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Skips the first `count` data events from this stream.

[skipWhile](stream/skipwhile)([bool](../dart-core/bool-class) test(T
element)) → [Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Skip data events from this stream while they are matched by `test`.

[take](stream/take)([int](../dart-core/int-class) count) →
[Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Provides at most the first `count` data events of this stream.

[takeWhile](stream/takewhile)([bool](../dart-core/bool-class) test(T
element)) → [Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Forwards data events while `test` is successful.

[timeout](stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void onTimeout([EventSink](eventsink-class)\<T\> sink)?}) →
[Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Creates a new stream with the same events as this stream.

[toList](stream/tolist)() →
[Future](future-class)\<[List](../dart-core/list-class)\<T\>\>

::: {.features}
inherited
:::

Collects all elements of this stream in a `List`.

[toSet](stream/toset)() →
[Future](future-class)\<[Set](../dart-core/set-class)\<T\>\>

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

[transform](stream/transform)\<S\>([StreamTransformer](streamtransformer-class)\<T,
S\> streamTransformer) → [Stream](stream-class)\<S\>

::: {.features}
inherited
:::

Applies `streamTransformer` to this stream.

[where](stream/where)([bool](../dart-core/bool-class) test(T event)) →
[Stream](stream-class)\<T\>

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamView-class.html>
:::
