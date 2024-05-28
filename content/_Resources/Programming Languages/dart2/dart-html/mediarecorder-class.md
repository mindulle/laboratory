[dart:html](../dart-html/dart-html-library){._links-link}

MediaRecorder class
===================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   MediaRecorder

Annotations

:   -   \@Native(\"MediaRecorder\")

Constructors
------------

[MediaRecorder](mediarecorder/mediarecorder)([MediaStream](mediastream-class)
stream, \[[Map](../dart-core/map-class)? options\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[audioBitsPerSecond](mediarecorder/audiobitspersecond) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[mimeType](mediarecorder/mimetype) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onError](mediarecorder/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onPause](mediarecorder/onpause) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[state](mediarecorder/state) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[stream](mediarecorder/stream) → [MediaStream](mediastream-class)?

::: {.features}
read-only
:::

[videoBitsPerSecond](mediarecorder/videobitspersecond) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pause](mediarecorder/pause)() → void

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[requestData](mediarecorder/requestdata)() → void

[resume](mediarecorder/resume)() → void

[start](mediarecorder/start)(\[[int](../dart-core/int-class)?
timeslice\]) → void

[stop](mediarecorder/stop)() → void

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

[isTypeSupported](mediarecorder/istypesupported)([String](../dart-core/string-class)
type) → [bool](../dart-core/bool-class)

Constants
---------

[errorEvent](mediarecorder/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[pauseEvent](mediarecorder/pauseevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('pause')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaRecorder-class.html>
:::
