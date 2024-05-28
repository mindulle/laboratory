[dart:developer](../dart-developer/dart-developer-library){._links-link}

Timeline class
==============

Add to the timeline.

[Timeline](timeline-class)\'s methods add synchronous events to the
timeline. When generating a timeline in Chrome\'s tracing format, using
[Timeline](timeline-class) generates \"Complete\" events.
[Timeline](timeline-class)\'s [startSync](timeline/startsync) and
[finishSync](timeline/finishsync) can be used explicitly, or implicitly
by wrapping a closure in [timeSync](timeline/timesync). For example:

``` {.language-dart data-language="dart"}
Timeline.startSync("Doing Something");
doSomething();
Timeline.finishSync();
```

Or:

``` {.language-dart data-language="dart"}
Timeline.timeSync("Doing Something", () {
  doSomething();
});
```

Constructors
------------

[Timeline](timeline/timeline)()

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

Static Properties
-----------------

[now](timeline/now) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The current time stamp from the clock used by the timeline. Units are
microseconds.

Static Methods
--------------

[finishSync](timeline/finishsync)() → void
:   Finish the last synchronous operation that was started.

[instantSync](timeline/instantsync)([String](../dart-core/string-class) name, {[Map](../dart-core/map-class)? arguments}) → void
:   Emit an instant event.

[startSync](timeline/startsync)([String](../dart-core/string-class) name, {[Map](../dart-core/map-class)? arguments, [Flow](flow-class)? flow}) → void
:   Start a synchronous operation labeled `name`. Optionally takes a
    [Map](../dart-core/map-class) of `arguments`. This slice may also
    optionally be associated with a [Flow](flow-class) event. This
    operation must be finished before returning to the event queue.

[timeSync](timeline/timesync)\<T\>([String](../dart-core/string-class) name, [TimelineSyncFunction](timelinesyncfunction)\<T\> function, {[Map](../dart-core/map-class)? arguments, [Flow](flow-class)? flow}) → T
:   A utility method to time a synchronous `function`. Internally calls
    `function` bracketed by calls to [startSync](timeline/startsync) and
    [finishSync](timeline/finishsync).

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Timeline-class.html>
:::
