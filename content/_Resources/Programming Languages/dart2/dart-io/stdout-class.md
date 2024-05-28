[dart:io](../dart-io/dart-io-library){._links-link}

Stdout class
============

An [IOSink](iosink-class) connected to either the standard out or error
of the process.

Provides a *blocking* `IOSink`, so using it to write will block until
the output is written.

In some situations this blocking behavior is undesirable as it does not
provide the same non-blocking behavior that `dart:io` in general
exposes. Use the property [nonBlocking](stdout/nonblocking) to get an
[IOSink](iosink-class) which has the non-blocking behavior.

This class can also be used to check whether `stdout` or `stderr` is
connected to a terminal and query some terminal properties.

The [addError](stdout/adderror) API is inherited from
[StreamSink](../dart-async/streamsink-class) and calling it will result
in an unhandled asynchronous error unless there is an error handler on
[done](stdout/done).

Implemented types

:   -   [IOSink](iosink-class)

Properties {#instance-properties}
----------

[done](stdout/done) → [Future](../dart-async/future-class)

::: {.features}
read-only, inherited
:::

A future that will complete when the consumer closes, or when an error
occurs.

[encoding](stdout/encoding) ↔ [Encoding](../dart-convert/encoding-class)

::: {.features}
read / write, inherited
:::

The [Encoding](../dart-convert/encoding-class) used when writing
strings.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hasTerminal](stdout/hasterminal) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether there is a terminal attached to stdout.

[nonBlocking](stdout/nonblocking) → [IOSink](iosink-class)

::: {.features}
read-only
:::

A non-blocking `IOSink` for the same output.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[supportsAnsiEscapes](stdout/supportsansiescapes) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether connected to a terminal that supports ANSI escape sequences.

[terminalColumns](stdout/terminalcolumns) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

The number of columns of the terminal.

[terminalLines](stdout/terminallines) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The number of lines of the terminal.

Methods {#instance-methods}
-------

[add](stdout/add)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
data) → void

::: {.features}
inherited
:::

Adds byte `data` to the target consumer, ignoring
[encoding](stdout/encoding).

[addError](stdout/adderror)([Object](../dart-core/object-class) error,
\[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) → void

::: {.features}
inherited
:::

Passes the error to the target consumer as an error event.

[addStream](stdout/addstream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
stream) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Adds all elements of the given `stream`.

[close](stdout/close)() → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Close the target consumer.

[flush](stdout/flush)() → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

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

[write](stdout/write)([Object](../dart-core/object-class)? object) →
void

::: {.features}
inherited
:::

Converts `object` to a String by invoking
[Object.toString](../dart-core/object/tostring) and [add](stdout/add)s
the encoding of the result to the target consumer.

[writeAll](stdout/writeall)([Iterable](../dart-core/iterable-class)
objects, \[[String](../dart-core/string-class) sep = \"\"\]) → void

::: {.features}
inherited
:::

Iterates over the given `objects` and [write](stdout/write)s them in
sequence.

[writeCharCode](stdout/writecharcode)([int](../dart-core/int-class)
charCode) → void

::: {.features}
inherited
:::

Writes the character of `charCode`.

[writeln](stdout/writeln)(\[[Object](../dart-core/object-class)? object
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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdout-class.html>
:::
