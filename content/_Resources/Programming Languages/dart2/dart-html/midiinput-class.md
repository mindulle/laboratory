[dart:html](../dart-html/dart-html-library){._links-link}

MidiInput class
===============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [MidiPort](midiport-class)
    -   MidiInput

Annotations

:   -   \@Native(\"MIDIInput\")

Properties {#instance-properties}
----------

[connection](midiport/connection) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](midiport/id) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[manufacturer](midiport/manufacturer) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[name](midiport/name) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onMidiMessage](midiinput/onmidimessage) →
[Stream](../dart-async/stream-class)\<[MidiMessageEvent](midimessageevent-class)\>

::: {.features}
read-only
:::

Stream of `midimessage` events handled by this
[MidiInput](midiinput-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[state](midiport/state) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[type](midiport/type) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[version](midiport/version) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[close](midiport/close)() → [Future](../dart-async/future-class)

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

[open](midiport/open)() → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

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

[midiMessageEvent](midiinput/midimessageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MidiMessageEvent](midimessageevent-class)\>
:   Static factory designed to expose `midimessage` events to event
    handlers that are not necessarily instances of
    [MidiInput](midiinput-class).
    <div>

    `const EventStreamProvider<MidiMessageEvent>('midimessage')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MidiInput-class.html>
:::
