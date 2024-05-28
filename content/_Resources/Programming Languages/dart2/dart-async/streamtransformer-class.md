[dart:async](../dart-async/dart-async-library){._links-link}

StreamTransformer\<S, T\> class
===============================

Transforms a Stream.

When a stream\'s [Stream.transform](stream/transform) method is invoked
with a [StreamTransformer](streamtransformer-class), the stream calls
the [bind](streamtransformer/bind) method on the provided transformer.
The resulting stream is then returned from the
[Stream.transform](stream/transform) method.

Conceptually, a transformer is simply a function from
[Stream](stream-class) to [Stream](stream-class) that is encapsulated
into a class.

It is good practice to write transformers that can be used multiple
times.

All other transforming methods on [Stream](stream-class), such as
[Stream.map](stream/map), [Stream.where](stream/where) or
[Stream.expand](stream/expand) can be implemented using
[Stream.transform](stream/transform). A
[StreamTransformer](streamtransformer-class) is thus very powerful but
often also a bit more complicated to use.

Implementers

:   -   [StreamTransformerBase](streamtransformerbase-class)
    -   [WebSocketTransformer](../dart-io/websockettransformer-class)

Constructors
------------

[StreamTransformer](streamtransformer/streamtransformer)([StreamSubscription](streamsubscription-class)\<T\>
onListen([Stream](stream-class)\<S\> stream,
[bool](../dart-core/bool-class) cancelOnError))

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Creates a [StreamTransformer](streamtransformer-class) based on the
given `onListen` callback.

[StreamTransformer.fromBind](streamtransformer/streamtransformer.frombind)([Stream](stream-class)\<T\>
bind([Stream](stream-class)\<S\>))

::: {.constructor-modifier .features}
factory
:::

Creates a [StreamTransformer](streamtransformer-class) based on a `bind`
callback.

[StreamTransformer.fromHandlers](streamtransformer/streamtransformer.fromhandlers)({void
handleData(S data, [EventSink](eventsink-class)\<T\> sink)?, void
handleError([Object](../dart-core/object-class) error,
[StackTrace](../dart-core/stacktrace-class) stackTrace,
[EventSink](eventsink-class)\<T\> sink)?, void
handleDone([EventSink](eventsink-class)\<T\> sink)?})

::: {.constructor-modifier .features}
factory
:::

Creates a [StreamTransformer](streamtransformer-class) that delegates
events to the given functions.

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

[bind](streamtransformer/bind)([Stream](stream-class)\<S\> stream) →
[Stream](stream-class)\<T\>

Transforms the provided `stream`.

[cast](streamtransformer/cast)\<RS, RT\>() →
[StreamTransformer](streamtransformer-class)\<RS, RT\>

Provides a `StreamTransformer<RS, RT>` view of this stream transformer.

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

Static Methods
--------------

[castFrom](streamtransformer/castfrom)\<SS, ST, TS, TT\>([StreamTransformer](streamtransformer-class)\<SS, ST\> source) → [StreamTransformer](streamtransformer-class)\<TS, TT\>
:   Adapts `source` to be a `StreamTransformer<TS, TT>`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamTransformer-class.html>
:::
