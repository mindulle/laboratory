[dart:html](../dart-html/dart-html-library){._links-link}

SpeechSynthesisUtterance class
==============================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   SpeechSynthesisUtterance

Annotations

:   -   \@Native(\"SpeechSynthesisUtterance\")

Constructors
------------

[SpeechSynthesisUtterance](speechsynthesisutterance/speechsynthesisutterance)(\[[String](../dart-core/string-class)?
text\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[lang](speechsynthesisutterance/lang) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onBoundary](speechsynthesisutterance/onboundary) →
[Stream](../dart-async/stream-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>

::: {.features}
read-only
:::

Stream of `boundary` events handled by this
[SpeechSynthesisUtterance](speechsynthesisutterance-class).

[onEnd](speechsynthesisutterance/onend) →
[Stream](../dart-async/stream-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>

::: {.features}
read-only
:::

Stream of `end` events handled by this
[SpeechSynthesisUtterance](speechsynthesisutterance-class).

[onError](speechsynthesisutterance/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this
[SpeechSynthesisUtterance](speechsynthesisutterance-class).

[onMark](speechsynthesisutterance/onmark) →
[Stream](../dart-async/stream-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>

::: {.features}
read-only
:::

Stream of `mark` events handled by this
[SpeechSynthesisUtterance](speechsynthesisutterance-class).

[onPause](speechsynthesisutterance/onpause) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `pause` events handled by this
[SpeechSynthesisUtterance](speechsynthesisutterance-class).

[onResume](speechsynthesisutterance/onresume) →
[Stream](../dart-async/stream-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>

::: {.features}
read-only
:::

Stream of `resume` events handled by this
[SpeechSynthesisUtterance](speechsynthesisutterance-class).

[onStart](speechsynthesisutterance/onstart) →
[Stream](../dart-async/stream-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>

::: {.features}
read-only
:::

Stream of `start` events handled by this
[SpeechSynthesisUtterance](speechsynthesisutterance-class).

[pitch](speechsynthesisutterance/pitch) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[rate](speechsynthesisutterance/rate) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[text](speechsynthesisutterance/text) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[voice](speechsynthesisutterance/voice) ↔
[SpeechSynthesisVoice](speechsynthesisvoice-class)?

::: {.features}
read / write
:::

[volume](speechsynthesisutterance/volume) ↔
[num](../dart-core/num-class)?

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

[boundaryEvent](speechsynthesisutterance/boundaryevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>
:   Static factory designed to expose `boundary` events to event
    handlers that are not necessarily instances of
    [SpeechSynthesisUtterance](speechsynthesisutterance-class).
    <div>

    `const EventStreamProvider<SpeechSynthesisEvent>('boundary')`

    </div>

[endEvent](speechsynthesisutterance/endevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>
:   Static factory designed to expose `end` events to event handlers
    that are not necessarily instances of
    [SpeechSynthesisUtterance](speechsynthesisutterance-class).
    <div>

    `const EventStreamProvider<SpeechSynthesisEvent>('end')`

    </div>

[errorEvent](speechsynthesisutterance/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [SpeechSynthesisUtterance](speechsynthesisutterance-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[markEvent](speechsynthesisutterance/markevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>
:   Static factory designed to expose `mark` events to event handlers
    that are not necessarily instances of
    [SpeechSynthesisUtterance](speechsynthesisutterance-class).
    <div>

    `const EventStreamProvider<SpeechSynthesisEvent>('mark')`

    </div>

[pauseEvent](speechsynthesisutterance/pauseevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `pause` events to event handlers
    that are not necessarily instances of
    [SpeechSynthesisUtterance](speechsynthesisutterance-class).
    <div>

    `const EventStreamProvider<Event>('pause')`

    </div>

[resumeEvent](speechsynthesisutterance/resumeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>
:   Static factory designed to expose `resume` events to event handlers
    that are not necessarily instances of
    [SpeechSynthesisUtterance](speechsynthesisutterance-class).
    <div>

    `const EventStreamProvider<SpeechSynthesisEvent>('resume')`

    </div>

[startEvent](speechsynthesisutterance/startevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechSynthesisEvent](speechsynthesisevent-class)\>
:   Static factory designed to expose `start` events to event handlers
    that are not necessarily instances of
    [SpeechSynthesisUtterance](speechsynthesisutterance-class).
    <div>

    `const EventStreamProvider<SpeechSynthesisEvent>('start')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechSynthesisUtterance-class.html>
:::
