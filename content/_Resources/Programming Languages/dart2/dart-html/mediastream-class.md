[dart:html](../dart-html/dart-html-library){._links-link}

MediaStream class
=================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   MediaStream

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@Native(\"MediaStream\")

Constructors
------------

[MediaStream](mediastream/mediastream)(\[dynamic stream\_OR\_tracks\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[active](mediastream/active) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](mediastream/id) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAddTrack](mediastream/onaddtrack) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `addtrack` events handled by this
[MediaStream](mediastream-class).

[onRemoveTrack](mediastream/onremovetrack) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `removetrack` events handled by this
[MediaStream](mediastream-class).

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

[addTrack](mediastream/addtrack)([MediaStreamTrack](mediastreamtrack-class)
track) → void

[clone](mediastream/clone)() → [MediaStream](mediastream-class)

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getAudioTracks](mediastream/getaudiotracks)() →
[List](../dart-core/list-class)\<[MediaStreamTrack](mediastreamtrack-class)\>

::: {.features}
\@Creates(\'JSExtendableArray\|MediaStreamTrack\'),
\@Returns(\'JSExtendableArray\')
:::

[getTrackById](mediastream/gettrackbyid)([String](../dart-core/string-class)
trackId) → [MediaStreamTrack](mediastreamtrack-class)?

[getTracks](mediastream/gettracks)() →
[List](../dart-core/list-class)\<[MediaStreamTrack](mediastreamtrack-class)\>

[getVideoTracks](mediastream/getvideotracks)() →
[List](../dart-core/list-class)\<[MediaStreamTrack](mediastreamtrack-class)\>

::: {.features}
\@Creates(\'JSExtendableArray\|MediaStreamTrack\'),
\@Returns(\'JSExtendableArray\')
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

[removeTrack](mediastream/removetrack)([MediaStreamTrack](mediastreamtrack-class)
track) → void

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

[supported](mediastream/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if the MediaStream APIs are supported on the current platform.

Constants
---------

[addTrackEvent](mediastream/addtrackevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `addtrack` events to event
    handlers that are not necessarily instances of
    [MediaStream](mediastream-class).
    <div>

    `const EventStreamProvider<Event>('addtrack')`

    </div>

[removeTrackEvent](mediastream/removetrackevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `removetrack` events to event
    handlers that are not necessarily instances of
    [MediaStream](mediastream-class).
    <div>

    `const EventStreamProvider<Event>('removetrack')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStream-class.html>
:::
