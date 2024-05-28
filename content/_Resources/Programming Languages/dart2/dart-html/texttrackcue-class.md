[dart:html](../dart-html/dart-html-library){._links-link}

TextTrackCue class
==================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   TextTrackCue

Implementers

:   -   [VttCue](vttcue-class)

Annotations

:   -   \@Native(\"TextTrackCue\")

Properties {#instance-properties}
----------

[endTime](texttrackcue/endtime) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](texttrackcue/id) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onEnter](texttrackcue/onenter) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `enter` events handled by this
[TextTrackCue](texttrackcue-class).

[onExit](texttrackcue/onexit) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `exit` events handled by this
[TextTrackCue](texttrackcue-class).

[pauseOnExit](texttrackcue/pauseonexit) ↔
[bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[startTime](texttrackcue/starttime) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[track](texttrackcue/track) → [TextTrack](texttrack-class)?

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

[enterEvent](texttrackcue/enterevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `enter` events to event handlers
    that are not necessarily instances of
    [TextTrackCue](texttrackcue-class).
    <div>

    `const EventStreamProvider<Event>('enter')`

    </div>

[exitEvent](texttrackcue/exitevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `exit` events to event handlers
    that are not necessarily instances of
    [TextTrackCue](texttrackcue-class).
    <div>

    `const EventStreamProvider<Event>('exit')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TextTrackCue-class.html>
:::
