[dart:html](../dart-html/dart-html-library){._links-link}

MediaStreamTrack class
======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   MediaStreamTrack

Implementers

:   -   [CanvasCaptureMediaStreamTrack](canvascapturemediastreamtrack-class)

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@Native(\"MediaStreamTrack\")

Properties {#instance-properties}
----------

[contentHint](mediastreamtrack/contenthint) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[enabled](mediastreamtrack/enabled) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](mediastreamtrack/id) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[kind](mediastreamtrack/kind) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[label](mediastreamtrack/label) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[muted](mediastreamtrack/muted) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
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
read-only
:::

Stream of `ended` events handled by this
[MediaStreamTrack](mediastreamtrack-class).

[onMute](mediastreamtrack/onmute) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `mute` events handled by this
[MediaStreamTrack](mediastreamtrack-class).

[onUnmute](mediastreamtrack/onunmute) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `unmute` events handled by this
[MediaStreamTrack](mediastreamtrack-class).

[readyState](mediastreamtrack/readystate) →
[String](../dart-core/string-class)?

::: {.features}
read-only
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

[clone](mediastreamtrack/clone)() →
[MediaStreamTrack](mediastreamtrack-class)

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getCapabilities](mediastreamtrack/getcapabilities)() →
[Map](../dart-core/map-class)

[getConstraints](mediastreamtrack/getconstraints)() →
[Map](../dart-core/map-class)

[getSettings](mediastreamtrack/getsettings)() →
[Map](../dart-core/map-class)

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

[stop](mediastreamtrack/stop)() → void

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

Constants
---------

[endedEvent](mediastreamtrack/endedevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `ended` events to event handlers
    that are not necessarily instances of
    [MediaStreamTrack](mediastreamtrack-class).
    <div>

    `const EventStreamProvider<Event>('ended')`

    </div>

[muteEvent](mediastreamtrack/muteevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `mute` events to event handlers
    that are not necessarily instances of
    [MediaStreamTrack](mediastreamtrack-class).
    <div>

    `const EventStreamProvider<Event>('mute')`

    </div>

[unmuteEvent](mediastreamtrack/unmuteevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `unmute` events to event handlers
    that are not necessarily instances of
    [MediaStreamTrack](mediastreamtrack-class).
    <div>

    `const EventStreamProvider<Event>('unmute')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStreamTrack-class.html>
:::
