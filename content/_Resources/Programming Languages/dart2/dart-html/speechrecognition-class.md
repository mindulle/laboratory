[dart:html](../dart-html/dart-html-library){._links-link}

SpeechRecognition class
=======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   SpeechRecognition

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME, \'25\')
    -   \@Native(\"SpeechRecognition\")

Constructors
------------

[SpeechRecognition](speechrecognition/speechrecognition)()

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[audioTrack](speechrecognition/audiotrack) ↔
[MediaStreamTrack](mediastreamtrack-class)?

::: {.features}
read / write
:::

[continuous](speechrecognition/continuous) ↔
[bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[grammars](speechrecognition/grammars) ↔
[SpeechGrammarList](speechgrammarlist-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[interimResults](speechrecognition/interimresults) ↔
[bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[lang](speechrecognition/lang) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[maxAlternatives](speechrecognition/maxalternatives) ↔
[int](../dart-core/int-class)?

::: {.features}
read / write
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAudioEnd](speechrecognition/onaudioend) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `audioend` events handled by this
[SpeechRecognition](speechrecognition-class).

[onAudioStart](speechrecognition/onaudiostart) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `audiostart` events handled by this
[SpeechRecognition](speechrecognition-class).

[onEnd](speechrecognition/onend) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `end` events handled by this
[SpeechRecognition](speechrecognition-class).

[onError](speechrecognition/onerror) →
[Stream](../dart-async/stream-class)\<[SpeechRecognitionError](speechrecognitionerror-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this
[SpeechRecognition](speechrecognition-class).

[onNoMatch](speechrecognition/onnomatch) →
[Stream](../dart-async/stream-class)\<[SpeechRecognitionEvent](speechrecognitionevent-class)\>

::: {.features}
read-only
:::

Stream of `nomatch` events handled by this
[SpeechRecognition](speechrecognition-class).

[onResult](speechrecognition/onresult) →
[Stream](../dart-async/stream-class)\<[SpeechRecognitionEvent](speechrecognitionevent-class)\>

::: {.features}
read-only
:::

Stream of `result` events handled by this
[SpeechRecognition](speechrecognition-class).

[onSoundEnd](speechrecognition/onsoundend) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `soundend` events handled by this
[SpeechRecognition](speechrecognition-class).

[onSoundStart](speechrecognition/onsoundstart) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `soundstart` events handled by this
[SpeechRecognition](speechrecognition-class).

[onSpeechEnd](speechrecognition/onspeechend) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `speechend` events handled by this
[SpeechRecognition](speechrecognition-class).

[onSpeechStart](speechrecognition/onspeechstart) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `speechstart` events handled by this
[SpeechRecognition](speechrecognition-class).

[onStart](speechrecognition/onstart) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `start` events handled by this
[SpeechRecognition](speechrecognition-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[abort](speechrecognition/abort)() → void

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

[start](speechrecognition/start)() → void

[stop](speechrecognition/stop)() → void

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

[supported](speechrecognition/supported) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Constants
---------

[audioEndEvent](speechrecognition/audioendevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `audioend` events to event
    handlers that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('audioend')`

    </div>

[audioStartEvent](speechrecognition/audiostartevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `audiostart` events to event
    handlers that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('audiostart')`

    </div>

[endEvent](speechrecognition/endevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `end` events to event handlers
    that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('end')`

    </div>

[errorEvent](speechrecognition/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechRecognitionError](speechrecognitionerror-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<SpeechRecognitionError>('error')`

    </div>

[noMatchEvent](speechrecognition/nomatchevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechRecognitionEvent](speechrecognitionevent-class)\>
:   Static factory designed to expose `nomatch` events to event handlers
    that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<SpeechRecognitionEvent>('nomatch')`

    </div>

[resultEvent](speechrecognition/resultevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[SpeechRecognitionEvent](speechrecognitionevent-class)\>
:   Static factory designed to expose `result` events to event handlers
    that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<SpeechRecognitionEvent>('result')`

    </div>

[soundEndEvent](speechrecognition/soundendevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `soundend` events to event
    handlers that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('soundend')`

    </div>

[soundStartEvent](speechrecognition/soundstartevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `soundstart` events to event
    handlers that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('soundstart')`

    </div>

[speechEndEvent](speechrecognition/speechendevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `speechend` events to event
    handlers that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('speechend')`

    </div>

[speechStartEvent](speechrecognition/speechstartevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `speechstart` events to event
    handlers that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('speechstart')`

    </div>

[startEvent](speechrecognition/startevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `start` events to event handlers
    that are not necessarily instances of
    [SpeechRecognition](speechrecognition-class).
    <div>

    `const EventStreamProvider<Event>('start')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition-class.html>
:::
