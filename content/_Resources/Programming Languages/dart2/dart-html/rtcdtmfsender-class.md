[dart:html](../dart-html/dart-html-library){._links-link}

RtcDtmfSender class
===================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   RtcDtmfSender

Annotations

:   -   \@Native(\"RTCDTMFSender\")

Properties {#instance-properties}
----------

[canInsertDtmf](rtcdtmfsender/caninsertdtmf) →
[bool](../dart-core/bool-class)?

::: {.features}
\@JSName(\'canInsertDTMF\'), read-only
:::

[duration](rtcdtmfsender/duration) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[interToneGap](rtcdtmfsender/intertonegap) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onToneChange](rtcdtmfsender/ontonechange) →
[Stream](../dart-async/stream-class)\<[RtcDtmfToneChangeEvent](rtcdtmftonechangeevent-class)\>

::: {.features}
read-only
:::

Stream of `tonechange` events handled by this
[RtcDtmfSender](rtcdtmfsender-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[toneBuffer](rtcdtmfsender/tonebuffer) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[track](rtcdtmfsender/track) →
[MediaStreamTrack](mediastreamtrack-class)?

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

[insertDtmf](rtcdtmfsender/insertdtmf)([String](../dart-core/string-class)
tones, \[[int](../dart-core/int-class)? duration,
[int](../dart-core/int-class)? interToneGap\]) → void

::: {.features}
\@JSName(\'insertDTMF\')
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

[toneChangeEvent](rtcdtmfsender/tonechangeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[RtcDtmfToneChangeEvent](rtcdtmftonechangeevent-class)\>
:   Static factory designed to expose `tonechange` events to event
    handlers that are not necessarily instances of
    [RtcDtmfSender](rtcdtmfsender-class).
    <div>

    `const EventStreamProvider<RtcDtmfToneChangeEvent>('tonechange')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcDtmfSender-class.html>
:::
