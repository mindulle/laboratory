[dart:html](../dart-html/dart-html-library){._links-link}

MidiPort class
==============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   MidiPort

Implementers

:   -   [MidiInput](midiinput-class)
    -   [MidiOutput](midioutput-class)

Annotations

:   -   \@Native(\"MIDIPort\")

Properties {#instance-properties}
----------

[connection](midiport/connection) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](midiport/id) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[manufacturer](midiport/manufacturer) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[name](midiport/name) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[state](midiport/state) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[type](midiport/type) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[version](midiport/version) → [String](../dart-core/string-class)?

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

[close](midiport/close)() → [Future](../dart-async/future-class)

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MidiPort-class.html>
:::
