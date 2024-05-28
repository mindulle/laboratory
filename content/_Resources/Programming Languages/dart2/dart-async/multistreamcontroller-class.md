[dart:async](../dart-async/dart-async-library){._links-link}

MultiStreamController\<T\> class
================================

An enhanced stream controller provided by
[Stream.multi](stream/stream.multi).

Acts like a normal asynchronous controller, but also allows adding
events synchronously. As with any synchronous event delivery, the sender
should be very careful to not deliver events at times when a new
listener might not be ready to receive them. That usually means only
delivering events synchronously in response to other asynchronous
events, because that is a time when an asynchronous event could happen.

Implemented types

:   -   [StreamController](streamcontroller-class)\<T\>

Annotations

:   -   \@Since(\"2.9\")

Constructors
------------

[MultiStreamController](multistreamcontroller/multistreamcontroller)()

Properties {#instance-properties}
----------

[done](streamcontroller/done) → [Future](future-class)

::: {.features}
read-only, inherited
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
read-only, inherited
:::

Whether there is a subscriber on the [Stream](stream-class).

[isClosed](streamcontroller/isclosed) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether the stream controller is closed for adding more events.

[isPaused](streamcontroller/ispaused) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether the subscription would need to buffer events.

[onCancel](streamcontroller/oncancel) ↔
([FutureOr](futureor-class)\<void\> Function?()?)

::: {.features}
read / write, inherited
:::

The callback which is called when the stream is canceled.

[onListen](streamcontroller/onlisten) ↔ (void Function?()?)

::: {.features}
read / write, inherited
:::

The callback which is called when the stream is listened to.

[onPause](streamcontroller/onpause) ↔ (void Function?()?)

::: {.features}
read / write, inherited
:::

The callback which is called when the stream is paused.

[onResume](streamcontroller/onresume) ↔ (void Function?()?)

::: {.features}
read / write, inherited
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
read-only, inherited
:::

Returns a view of this object that only exposes the
[StreamSink](streamsink-class) interface.

[stream](streamcontroller/stream) → [Stream](stream-class)\<T\>

::: {.features}
read-only, inherited
:::

The stream that this controller is controlling.

Methods {#instance-methods}
-------

[add](streamcontroller/add)(T event) → void

::: {.features}
inherited
:::

Sends a data `event`.

[addError](streamcontroller/adderror)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

::: {.features}
inherited
:::

Sends or enqueues an error event.

[addErrorSync](multistreamcontroller/adderrorsync)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

Adds and delivers an error event.

[addStream](streamcontroller/addstream)([Stream](stream-class)\<T\>
source, {[bool](../dart-core/bool-class)? cancelOnError}) →
[Future](future-class)

::: {.features}
inherited
:::

Receives events from `source` and puts them into this controller\'s
stream.

[addSync](multistreamcontroller/addsync)(T value) → void

Adds and delivers an event.

[close](streamcontroller/close)() → [Future](future-class)

::: {.features}
inherited
:::

Closes the stream.

[closeSync](multistreamcontroller/closesync)() → void

Closes the controller and delivers a done event.

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
<https://api.dart.dev/stable/2.18.5/dart-async/MultiStreamController-class.html>
:::
