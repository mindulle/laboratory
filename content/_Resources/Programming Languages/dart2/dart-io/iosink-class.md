[dart:io](../dart-io/dart-io-library){._links-link}

IOSink class
============

A combined byte and text output.

An [IOSink](iosink-class) combines a
[StreamSink](../dart-async/streamsink-class) of bytes with a
[StringSink](../dart-core/stringsink-class), and allows easy output of
both bytes and text.

Writing text ([write](iosink/write)) and adding bytes
([add](iosink/add)) may be interleaved freely.

While a stream is being added using [addStream](iosink/addstream), any
further attempts to add or write to the [IOSink](iosink-class) will fail
until the [addStream](iosink/addstream) completes.

It is an error to add data to the [IOSink](iosink-class) after the sink
is closed.

Implemented types

:   -   [StreamSink](../dart-async/streamsink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [StringSink](../dart-core/stringsink-class)

Implementers

:   -   [HttpClientRequest](httpclientrequest-class)
    -   [HttpResponse](httpresponse-class)
    -   [Socket](socket-class)
    -   [Stdout](stdout-class)

Constructors
------------

[IOSink](iosink/iosink)([StreamConsumer](../dart-async/streamconsumer-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
target, {[Encoding](../dart-convert/encoding-class) encoding = utf8})

::: {.constructor-modifier .features}
factory
:::

Create an [IOSink](iosink-class) that outputs to a `target`
[StreamConsumer](../dart-async/streamconsumer-class) of bytes.

Properties {#instance-properties}
----------

[done](iosink/done) → [Future](../dart-async/future-class)

::: {.features}
read-only, override
:::

A future that will complete when the consumer closes, or when an error
occurs.

[encoding](iosink/encoding) ↔ [Encoding](../dart-convert/encoding-class)

::: {.features}
read / write
:::

The [Encoding](../dart-convert/encoding-class) used when writing
strings.

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

[add](iosink/add)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
data) → void

::: {.features}
override
:::

Adds byte `data` to the target consumer, ignoring
[encoding](iosink/encoding).

[addError](iosink/adderror)([Object](../dart-core/object-class) error,
\[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) → void

::: {.features}
override
:::

Passes the error to the target consumer as an error event.

[addStream](iosink/addstream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
stream) → [Future](../dart-async/future-class)

::: {.features}
override
:::

Adds all elements of the given `stream`.

[close](iosink/close)() → [Future](../dart-async/future-class)

::: {.features}
override
:::

Close the target consumer.

[flush](iosink/flush)() → [Future](../dart-async/future-class)

Returns a [Future](../dart-async/future-class) that completes once all
buffered data is accepted by the underlying
[StreamConsumer](../dart-async/streamconsumer-class).

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

[write](iosink/write)([Object](../dart-core/object-class)? object) →
void

::: {.features}
override
:::

Converts `object` to a String by invoking
[Object.toString](../dart-core/object/tostring) and [add](iosink/add)s
the encoding of the result to the target consumer.

[writeAll](iosink/writeall)([Iterable](../dart-core/iterable-class)
objects, \[[String](../dart-core/string-class) separator = \"\"\]) →
void

::: {.features}
override
:::

Iterates over the given `objects` and [write](iosink/write)s them in
sequence.

[writeCharCode](iosink/writecharcode)([int](../dart-core/int-class)
charCode) → void

::: {.features}
override
:::

Writes the character of `charCode`.

[writeln](iosink/writeln)(\[[Object](../dart-core/object-class)? object
= \"\"\]) → void

::: {.features}
override
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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOSink-class.html>
:::
