[dart:async](../dart-async/dart-async-library){._links-link}

EventSink\<T\> class
====================

A [Sink](../dart-core/sink-class) that supports adding errors.

This makes it suitable for capturing the results of asynchronous
computations, which can complete with a value or an error.

The [EventSink](eventsink-class) has been designed to handle
asynchronous events from [Stream](stream-class)s. See, for example,
[Stream.eventTransformed](stream/stream.eventtransformed) which uses
`EventSink`s to transform events.

Implemented types

:   -   [Sink](../dart-core/sink-class)\<T\>

Implementers

:   -   [StreamSink](streamsink-class)

Constructors
------------

[EventSink](eventsink/eventsink)()

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

[add](eventsink/add)(T event) → void

::: {.features}
override
:::

Adds a data `event` to the sink.

[addError](eventsink/adderror)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

Adds an `error` to the sink.

[close](eventsink/close)() → void

::: {.features}
override
:::

Closes the sink.

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
<https://api.dart.dev/stable/2.18.5/dart-async/EventSink-class.html>
:::
