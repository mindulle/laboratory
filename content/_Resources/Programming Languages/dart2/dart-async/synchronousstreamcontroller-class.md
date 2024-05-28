[dart:async](../dart-async/dart-async-library){._links-link}

SynchronousStreamController\<T\> class
======================================

A stream controller that delivers its events synchronously.

A synchronous stream controller is intended for cases where an already
asynchronous event triggers an event on a stream.

Instead of adding the event to the stream in a later microtask, causing
extra latency, the event is instead fired immediately by the synchronous
stream controller, as if the stream event was the current event or
microtask.

The synchronous stream controller can be used to break the contract on
[Stream](stream-class), and it must be used carefully to avoid doing so.

The only advantage to using a
[SynchronousStreamController](synchronousstreamcontroller-class) over a
normal [StreamController](streamcontroller-class) is the improved
latency. Only use the synchronous version if the improvement is
significant, and if its use is safe. Otherwise just use a normal stream
controller, which will always have the correct behavior for a
[Stream](stream-class), and won\'t accidentally break other code.

Adding events to a synchronous controller should only happen as the very
last part of the handling of the original event. At that point, adding
an event to the stream is equivalent to returning to the event loop and
adding the event in the next microtask.

Each listener callback will be run as if it was a top-level event or
microtask. This means that if it throws, the error will be reported as
uncaught as soon as possible. This is one reason to add the event as the
last thing in the original event handler -- any action done after adding
the event will delay the report of errors in the event listener
callbacks.

If an event is added in a setting that isn\'t known to be another event,
it may cause the stream\'s listener to get that event before the
listener is ready to handle it. We promise that after calling
[Stream.listen](stream/listen), you won\'t get any events until the code
doing the listen has completed. Calling
[add](synchronousstreamcontroller/add) in response to a function call of
unknown origin may break that promise.

An [onListen](streamcontroller/onlisten) callback from the controller is
*not* an asynchronous event, and adding events to the controller in the
`onListen` callback is always wrong. The events will be delivered before
the listener has even received the subscription yet.

The synchronous broadcast stream controller also has a restrictions that
a normal stream controller does not: The
[add](synchronousstreamcontroller/add),
[addError](synchronousstreamcontroller/adderror),
[close](synchronousstreamcontroller/close) and
[addStream](streamcontroller/addstream) methods *must not* be called
while an event is being delivered. That is, if a callback on a
subscription on the controller\'s stream causes a call to any of the
functions above, the call will fail. A broadcast stream may have more
than one listener, and if an event is added synchronously while another
is being also in the process of being added, the latter event might
reach some listeners before the former. To prevent that, an event cannot
be added while a previous event is being fired. This guarantees that an
event is fully delivered when the first
[add](synchronousstreamcontroller/add),
[addError](synchronousstreamcontroller/adderror) or
[close](synchronousstreamcontroller/close) returns, and further events
will be delivered in the correct order.

This still only guarantees that the event is delivered to the
subscription. If the subscription is paused, the actual callback may
still happen later, and the event will instead be buffered by the
subscription. Barring pausing, and the following buffered events that
haven\'t been delivered yet, callbacks will be called synchronously when
an event is added.

Adding an event to a synchronous non-broadcast stream controller while
another event is in progress may cause the second event to be delayed
and not be delivered synchronously, and until that event is delivered,
the controller will not act synchronously.

Implemented types

:   -   [StreamController](streamcontroller-class)\<T\>

Constructors
------------

[SynchronousStreamController](synchronousstreamcontroller/synchronousstreamcontroller)()

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

[add](synchronousstreamcontroller/add)(T data) → void

::: {.features}
override
:::

Adds event to the controller\'s stream.

[addError](synchronousstreamcontroller/adderror)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

::: {.features}
override
:::

Adds error to the controller\'s stream.

[addStream](streamcontroller/addstream)([Stream](stream-class)\<T\>
source, {[bool](../dart-core/bool-class)? cancelOnError}) →
[Future](future-class)

::: {.features}
inherited
:::

Receives events from `source` and puts them into this controller\'s
stream.

[close](synchronousstreamcontroller/close)() → [Future](future-class)

::: {.features}
override
:::

Closes the controller\'s stream.

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
<https://api.dart.dev/stable/2.18.5/dart-async/SynchronousStreamController-class.html>
:::
