[dart:html](../dart-html/dart-html-library){._links-link}

CanvasCaptureMediaStreamTrack class
===================================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [MediaStreamTrack](mediastreamtrack-class)
    -   CanvasCaptureMediaStreamTrack

Annotations

:   -   \@Native(\"CanvasCaptureMediaStreamTrack\")

Properties {#instance-properties}
----------

[canvas](canvascapturemediastreamtrack/canvas) →
[CanvasElement](canvaselement-class)?

::: {.features}
read-only
:::

[contentHint](mediastreamtrack/contenthint) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[enabled](mediastreamtrack/enabled) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](mediastreamtrack/id) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[kind](mediastreamtrack/kind) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[label](mediastreamtrack/label) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[muted](mediastreamtrack/muted) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onEnded](mediastreamtrack/onended) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `ended` events handled by this
[MediaStreamTrack](mediastreamtrack-class).

[onMute](mediastreamtrack/onmute) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mute` events handled by this
[MediaStreamTrack](mediastreamtrack-class).

[onUnmute](mediastreamtrack/onunmute) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `unmute` events handled by this
[MediaStreamTrack](mediastreamtrack-class).

[readyState](mediastreamtrack/readystate) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[applyConstraints](mediastreamtrack/applyconstraints)(\[[Map](../dart-core/map-class)?
constraints\]) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

[clone](mediastreamtrack/clone)() →
[MediaStreamTrack](mediastreamtrack-class)

::: {.features}
inherited
:::

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getCapabilities](mediastreamtrack/getcapabilities)() →
[Map](../dart-core/map-class)

::: {.features}
inherited
:::

[getConstraints](mediastreamtrack/getconstraints)() →
[Map](../dart-core/map-class)

::: {.features}
inherited
:::

[getSettings](mediastreamtrack/getsettings)() →
[Map](../dart-core/map-class)

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[requestFrame](canvascapturemediastreamtrack/requestframe)() → void

[stop](mediastreamtrack/stop)() → void

::: {.features}
inherited
:::

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
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasCaptureMediaStreamTrack-class.html>
:::
