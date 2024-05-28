[dart:async](../dart-async/dart-async-library){._links-link}

StreamSink\<S\> class
=====================

A object that accepts stream events both synchronously and
asynchronously.

A [StreamSink](streamsink-class) combines the methods from
[StreamConsumer](streamconsumer-class) and [EventSink](eventsink-class).

The [EventSink](eventsink-class) methods can\'t be used while the
[addStream](streamconsumer/addstream) is called. As soon as the
[addStream](streamconsumer/addstream)\'s [Future](future-class)
completes with a value, the [EventSink](eventsink-class) methods can be
used again.

If [addStream](streamconsumer/addstream) is called after any of the
[EventSink](eventsink-class) methods, it\'ll be delayed until the
underlying system has consumed the data added by the
[EventSink](eventsink-class) methods.

When [EventSink](eventsink-class) methods are used, the
[done](streamsink/done) [Future](future-class) can be used to catch any
errors.

When [close](streamsink/close) is called, it will return the
[done](streamsink/done) [Future](future-class).

Implemented types

:   -   [EventSink](eventsink-class)\<S\>
    -   [StreamConsumer](streamconsumer-class)\<S\>

Implementers

:   -   [IOSink](../dart-io/iosink-class)
    -   [StreamController](streamcontroller-class)
    -   [WebSocket](../dart-io/websocket-class)

Constructors
------------

[StreamSink](streamsink/streamsink)()

Properties {#instance-properties}
----------

[done](streamsink/done) → [Future](future-class)

::: {.features}
read-only
:::

Return a future which is completed when the
[StreamSink](streamsink-class) is finished.

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

[add](eventsink/add)(S event) → void

::: {.features}
inherited
:::

Adds a data `event` to the sink.

[addError](eventsink/adderror)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

::: {.features}
inherited
:::

Adds an `error` to the sink.

[addStream](streamconsumer/addstream)([Stream](stream-class)\<S\>
stream) → [Future](future-class)

::: {.features}
inherited
:::

Consumes the elements of `stream`.

[close](streamsink/close)() → [Future](future-class)

::: {.features}
override
:::

Tells the stream sink that no further streams will be added.

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSink-class.html>
:::
