[dart:async](../dart-async/dart-async-library){._links-link}

StreamController\<T\> class
===========================

A controller with the stream it controls.

This controller allows sending data, error and done events on its
[stream](streamcontroller/stream).

This class can be used to create a simple stream that others can listen
on, and to push events to that stream.

It\'s possible to check whether the stream is paused or not, and whether
it has subscribers or not, as well as getting a callback when either of
these change.

Example:

``` {.language-dart data-language="dart"}
final streamController = StreamController(
  onPause: () => print('Paused'),
  onResume: () => print('Resumed'),
  onCancel: () => print('Cancelled'),
  onListen: () => print('Listens'),
);

streamController.stream.listen(
  (event) => print('Event: $event'),
  onDone: () => print('Done'),
  onError: (error) => print(error),
);
```

To check whether there is a subscriber on the stream, use
[hasListener](streamcontroller/haslistener).

``` {.language-dart data-language="dart"}
var hasListener = streamController.hasListener; // true
```

To send data events to the stream, use [add](streamcontroller/add) or
[addStream](streamcontroller/addstream).

``` {.language-dart data-language="dart"}
streamController.add(999);
final stream = Stream<int>.periodic(
    const Duration(milliseconds: 200), (count) => count * count).take(4);
await streamController.addStream(stream);
```

To send an error event to the stream, use
[addError](streamcontroller/adderror) or
[addStream](streamcontroller/addstream).

``` {.language-dart data-language="dart"}
streamController.addError(Exception('Issue 101'));
await streamController.addStream(Stream.error(Exception('Issue 404')));
```

To check whether the stream is closed, use
[isClosed](streamcontroller/isclosed).

``` {.language-dart data-language="dart"}
var isClosed = streamController.isClosed; // false
```

To close the stream, use [close](streamcontroller/close).

``` {.language-dart data-language="dart"}
await streamController.close();
isClosed = streamController.isClosed; // true
```

Implemented types

:   -   [StreamSink](streamsink-class)\<T\>

Implementers

:   -   [MultiStreamController](multistreamcontroller-class)
    -   [SynchronousStreamController](synchronousstreamcontroller-class)

Constructors
------------

[StreamController](streamcontroller/streamcontroller)({void onListen()?,
void onPause()?, void onResume()?, [FutureOr](futureor-class)\<void\>
onCancel()?, [bool](../dart-core/bool-class) sync = false})

::: {.constructor-modifier .features}
factory
:::

A controller with a [stream](streamcontroller/stream) that supports only
one single subscriber.

[StreamController.broadcast](streamcontroller/streamcontroller.broadcast)({void
onListen()?, void onCancel()?, [bool](../dart-core/bool-class) sync =
false})

::: {.constructor-modifier .features}
factory
:::

A controller where [stream](streamcontroller/stream) can be listened to
more than once.

Properties {#instance-properties}
----------

[done](streamcontroller/done) → [Future](future-class)

::: {.features}
read-only, override
:::

A future which is completed when the stream controller is done sending
events.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hasListener](streamcontroller/haslistener) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether there is a subscriber on the [Stream](stream-class).

[isClosed](streamcontroller/isclosed) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the stream controller is closed for adding more events.

[isPaused](streamcontroller/ispaused) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the subscription would need to buffer events.

[onCancel](streamcontroller/oncancel) ↔
([FutureOr](futureor-class)\<void\> Function?()?)

::: {.features}
read / write
:::

The callback which is called when the stream is canceled.

[onListen](streamcontroller/onlisten) ↔ (void Function?()?)

::: {.features}
read / write
:::

The callback which is called when the stream is listened to.

[onPause](streamcontroller/onpause) ↔ (void Function?()?)

::: {.features}
read / write
:::

The callback which is called when the stream is paused.

[onResume](streamcontroller/onresume) ↔ (void Function?()?)

::: {.features}
read / write
:::

The callback which is called when the stream is resumed.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sink](streamcontroller/sink) → [StreamSink](streamsink-class)\<T\>

::: {.features}
read-only
:::

Returns a view of this object that only exposes the
[StreamSink](streamsink-class) interface.

[stream](streamcontroller/stream) → [Stream](stream-class)\<T\>

::: {.features}
read-only
:::

The stream that this controller is controlling.

Methods {#instance-methods}
-------

[add](streamcontroller/add)(T event) → void

::: {.features}
override
:::

Sends a data `event`.

[addError](streamcontroller/adderror)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

::: {.features}
override
:::

Sends or enqueues an error event.

[addStream](streamcontroller/addstream)([Stream](stream-class)\<T\>
source, {[bool](../dart-core/bool-class)? cancelOnError}) →
[Future](future-class)

::: {.features}
override
:::

Receives events from `source` and puts them into this controller\'s
stream.

[close](streamcontroller/close)() → [Future](future-class)

::: {.features}
override
:::

Closes the stream.

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
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController-class.html>
:::
