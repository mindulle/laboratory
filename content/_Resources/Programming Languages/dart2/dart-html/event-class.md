[dart:html](../dart-html/dart-html-library){._links-link}

Event class
===========

Implementers

:   -   [AnimationEvent](animationevent-class)
    -   [AnimationPlaybackEvent](animationplaybackevent-class)
    -   [ApplicationCacheErrorEvent](applicationcacheerrorevent-class)
    -   [AudioProcessingEvent](../dart-web_audio/audioprocessingevent-class)
    -   [BeforeInstallPromptEvent](beforeinstallpromptevent-class)
    -   [BeforeUnloadEvent](beforeunloadevent-class)
    -   [BlobEvent](blobevent-class)
    -   [ClipboardEvent](clipboardevent-class)
    -   [CloseEvent](closeevent-class)
    -   [ContextEvent](../dart-web_gl/contextevent-class)
    -   [CustomEvent](customevent-class)
    -   [DeviceMotionEvent](devicemotionevent-class)
    -   [DeviceOrientationEvent](deviceorientationevent-class)
    -   [ErrorEvent](errorevent-class)
    -   [ExtendableEvent](extendableevent-class)
    -   [FontFaceSetLoadEvent](fontfacesetloadevent-class)
    -   [GamepadEvent](gamepadevent-class)
    -   [HashChangeEvent](hashchangeevent-class)
    -   [KeyEvent](keyevent-class)
    -   [MediaEncryptedEvent](mediaencryptedevent-class)
    -   [MediaKeyMessageEvent](mediakeymessageevent-class)
    -   [MediaQueryListEvent](mediaquerylistevent-class)
    -   [MediaStreamEvent](mediastreamevent-class)
    -   [MediaStreamTrackEvent](mediastreamtrackevent-class)
    -   [MessageEvent](messageevent-class)
    -   [MidiConnectionEvent](midiconnectionevent-class)
    -   [MidiMessageEvent](midimessageevent-class)
    -   [MutationEvent](mutationevent-class){.deprecated}
    -   [OfflineAudioCompletionEvent](../dart-web_audio/offlineaudiocompletionevent-class)
    -   [PageTransitionEvent](pagetransitionevent-class)
    -   [PaymentRequestUpdateEvent](paymentrequestupdateevent-class)
    -   [PopStateEvent](popstateevent-class)
    -   [PresentationConnectionAvailableEvent](presentationconnectionavailableevent-class)
    -   [PresentationConnectionCloseEvent](presentationconnectioncloseevent-class)
    -   [ProgressEvent](progressevent-class)
    -   [PromiseRejectionEvent](promiserejectionevent-class)
    -   [RtcDataChannelEvent](rtcdatachannelevent-class)
    -   [RtcDtmfToneChangeEvent](rtcdtmftonechangeevent-class)
    -   [RtcPeerConnectionIceEvent](rtcpeerconnectioniceevent-class)
    -   [RtcTrackEvent](rtctrackevent-class)
    -   [SecurityPolicyViolationEvent](securitypolicyviolationevent-class)
    -   [SensorErrorEvent](sensorerrorevent-class)
    -   [SpeechRecognitionError](speechrecognitionerror-class)
    -   [SpeechRecognitionEvent](speechrecognitionevent-class)
    -   [SpeechSynthesisEvent](speechsynthesisevent-class)
    -   [StorageEvent](storageevent-class)
    -   [TrackEvent](trackevent-class)
    -   [TransitionEvent](transitionevent-class)
    -   [UIEvent](uievent-class)
    -   [VersionChangeEvent](../dart-indexed_db/versionchangeevent-class)
    -   [VRDeviceEvent](vrdeviceevent-class)
    -   [VRDisplayEvent](vrdisplayevent-class)
    -   [VRSessionEvent](vrsessionevent-class)

Annotations

:   -   \@Native(\"Event,InputEvent,SubmitEvent\")

Constructors
------------

[Event](event/event)([String](../dart-core/string-class) type,
{[bool](../dart-core/bool-class) canBubble = true,
[bool](../dart-core/bool-class) cancelable = true})

::: {.constructor-modifier .features}
factory
:::

[Event.eventType](event/event.eventtype)([String](../dart-core/string-class)
type, [String](../dart-core/string-class) name,
{[bool](../dart-core/bool-class) canBubble = true,
[bool](../dart-core/bool-class) cancelable = true})

::: {.constructor-modifier .features}
factory
:::

Creates a new Event object of the specified type.

Properties {#instance-properties}
----------

[bubbles](event/bubbles) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[cancelable](event/cancelable) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[composed](event/composed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[currentTarget](event/currenttarget) → [EventTarget](eventtarget-class)?

::: {.features}
read-only
:::

[defaultPrevented](event/defaultprevented) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[eventPhase](event/eventphase) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isTrusted](event/istrusted) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[matchingTarget](event/matchingtarget) → [Element](element-class)

::: {.features}
read-only
:::

A pointer to the element whose CSS selector matched within which an
event was fired. If this Event was not associated with any Event
delegation, accessing this value will throw an
[UnsupportedError](../dart-core/unsupportederror-class).

[path](event/path) →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[target](event/target) → [EventTarget](eventtarget-class)?

::: {.features}
read-only
:::

[timeStamp](event/timestamp) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[type](event/type) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[composedPath](event/composedpath)() →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[preventDefault](event/preventdefault)() → void

[stopImmediatePropagation](event/stopimmediatepropagation)() → void

[stopPropagation](event/stoppropagation)() → void

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

[AT\_TARGET](event/at_target-constant) → const [int](../dart-core/int-class)
:   This event is being handled by the event target.
    <div>

    `2`

    </div>

[BUBBLING\_PHASE](event/bubbling_phase-constant) → const [int](../dart-core/int-class)
:   This event is bubbling up through the target\'s ancestors.
    <div>

    `3`

    </div>

[CAPTURING\_PHASE](event/capturing_phase-constant) → const [int](../dart-core/int-class)
:   This event is propagating through the target\'s ancestors, starting
    from the document.
    <div>

    `1`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Event-class.html>
:::
