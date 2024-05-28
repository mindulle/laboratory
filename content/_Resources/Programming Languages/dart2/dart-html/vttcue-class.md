[dart:html](../dart-html/dart-html-library){._links-link}

VttCue class
============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [TextTrackCue](texttrackcue-class)
    -   VttCue

Annotations

:   -   \@Native(\"VTTCue\")

Constructors
------------

[VttCue](vttcue/vttcue)([num](../dart-core/num-class) startTime,
[num](../dart-core/num-class) endTime,
[String](../dart-core/string-class) text)

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[align](vttcue/align) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[endTime](texttrackcue/endtime) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](texttrackcue/id) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[line](vttcue/line) ↔ [Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'Null\'), \@Returns(\'num\|String\'), read / write
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
read-only, inherited
:::

Stream of `enter` events handled by this
[TextTrackCue](texttrackcue-class).

[onExit](texttrackcue/onexit) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `exit` events handled by this
[TextTrackCue](texttrackcue-class).

[pauseOnExit](texttrackcue/pauseonexit) ↔
[bool](../dart-core/bool-class)?

::: {.features}
read / write, inherited
:::

[position](vttcue/position) ↔ [Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'Null\'), \@Returns(\'num\|String\'), read / write
:::

[region](vttcue/region) ↔ [VttRegion](vttregion-class)?

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[size](vttcue/size) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[snapToLines](vttcue/snaptolines) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[startTime](texttrackcue/starttime) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write, inherited
:::

[text](vttcue/text) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[track](texttrackcue/track) → [TextTrack](texttrack-class)?

::: {.features}
read-only, inherited
:::

[vertical](vttcue/vertical) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
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

[getCueAsHtml](vttcue/getcueashtml)() →
[DocumentFragment](documentfragment-class)

::: {.features}
\@JSName(\'getCueAsHTML\')
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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/VttCue-class.html>
:::
