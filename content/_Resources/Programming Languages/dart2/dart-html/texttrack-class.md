[dart:html](../dart-html/dart-html-library){._links-link}

TextTrack class
===============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   TextTrack

Annotations

:   -   \@Native(\"TextTrack\")

Properties {#instance-properties}
----------

[activeCues](texttrack/activecues) →
[TextTrackCueList](texttrackcuelist-class)?

::: {.features}
read-only
:::

[cues](texttrack/cues) → [TextTrackCueList](texttrackcuelist-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](texttrack/id) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[kind](texttrack/kind) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[label](texttrack/label) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[language](texttrack/language) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[mode](texttrack/mode) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onCueChange](texttrack/oncuechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `cuechange` events handled by this
[TextTrack](texttrack-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[addCue](texttrack/addcue)([TextTrackCue](texttrackcue-class) cue) →
void

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

[removeCue](texttrack/removecue)([TextTrackCue](texttrackcue-class) cue)
→ void

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

[cueChangeEvent](texttrack/cuechangeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `cuechange` events to event
    handlers that are not necessarily instances of
    [TextTrack](texttrack-class).
    <div>

    `const EventStreamProvider<Event>('cuechange')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TextTrack-class.html>
:::
