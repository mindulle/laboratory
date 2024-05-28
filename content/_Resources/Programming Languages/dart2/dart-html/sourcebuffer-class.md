[dart:html](../dart-html/dart-html-library){._links-link}

SourceBuffer class
==================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   SourceBuffer

Annotations

:   -   \@Native(\"SourceBuffer\")

Properties {#instance-properties}
----------

[appendWindowEnd](sourcebuffer/appendwindowend) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[appendWindowStart](sourcebuffer/appendwindowstart) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[audioTracks](sourcebuffer/audiotracks) →
[AudioTrackList](../dart-web_audio/audiotracklist-class)?

::: {.features}
read-only
:::

[buffered](sourcebuffer/buffered) → [TimeRanges](timeranges-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[mode](sourcebuffer/mode) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](sourcebuffer/onabort) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onError](sourcebuffer/onerror) →
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

[timestampOffset](sourcebuffer/timestampoffset) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[trackDefaults](sourcebuffer/trackdefaults) ↔
[TrackDefaultList](trackdefaultlist-class)?

::: {.features}
read / write
:::

[updating](sourcebuffer/updating) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[videoTracks](sourcebuffer/videotracks) →
[VideoTrackList](videotracklist-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[abort](sourcebuffer/abort)() → void

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[appendBuffer](sourcebuffer/appendbuffer)([ByteBuffer](../dart-typed_data/bytebuffer-class)
data) → void

[appendTypedData](sourcebuffer/appendtypeddata)([TypedData](../dart-typed_data/typeddata-class)
data) → void

::: {.features}
\@JSName(\'appendBuffer\')
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

[remove](sourcebuffer/remove)([num](../dart-core/num-class) start,
[num](../dart-core/num-class) end) → void

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

[abortEvent](sourcebuffer/abortevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('abort')`

    </div>

[errorEvent](sourcebuffer/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('error')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SourceBuffer-class.html>
:::
