[dart:async](../dart-async/dart-async-library){._links-link}

StreamSubscription\<T\> class
=============================

A subscription on events from a [Stream](stream-class).

When you listen on a [Stream](stream-class) using
[Stream.listen](stream/listen), a
[StreamSubscription](streamsubscription-class) object is returned.

The subscription provides events to the listener, and holds the
callbacks used to handle the events. The subscription can also be used
to unsubscribe from the events, or to temporarily pause the events from
the stream.

Example:

``` {.language-dart data-language="dart"}
final stream = Stream.periodic(const Duration(seconds: 1), (i) => i * i)
    .take(10);

final subscription = stream.listen(print); // A StreamSubscription<int>.
```

To pause the subscription, use [pause](streamsubscription/pause).

``` {.language-dart data-language="dart"}
// Do some work.
subscription.pause();
print(subscription.isPaused); // true
```

To resume after the pause, use [resume](streamsubscription/resume).

``` {.language-dart data-language="dart"}
// Do some work.
subscription.resume();
print(subscription.isPaused); // false
```

To cancel the subscription, use [cancel](streamsubscription/cancel).

``` {.language-dart data-language="dart"}
// Do some work.
subscription.cancel();
```

Constructors
------------

[StreamSubscription](streamsubscription/streamsubscription)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isPaused](streamsubscription/ispaused) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the [StreamSubscription](streamsubscription-class) is currently
paused.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[asFuture](streamsubscription/asfuture)\<E\>(\[E? futureValue\]) →
[Future](future-class)\<E\>

Returns a future that handles the [onDone](streamsubscription/ondone)
and [onError](streamsubscription/onerror) callbacks.

[cancel](streamsubscription/cancel)() → [Future](future-class)\<void\>

Cancels this subscription.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[onData](streamsubscription/ondata)(void handleData(T data)?) → void

Replaces the data event handler of this subscription.

[onDone](streamsubscription/ondone)(void handleDone()?) → void

Replaces the done event handler of this subscription.

[onError](streamsubscription/onerror)([Function](../dart-core/function-class)?
handleError) → void

Replaces the error event handler of this subscription.

[pause](streamsubscription/pause)(\[[Future](future-class)\<void\>?
resumeSignal\]) → void

Requests that the stream pauses events until further notice.

[resume](streamsubscription/resume)() → void

Resumes after a pause.

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
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSubscription-class.html>
:::
