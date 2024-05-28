[dart:html](../dart-html/dart-html-library){._links-link}

EventTarget class
=================

Base class for all browser objects that support events.

Use the [on](eventtarget/on) property to add, and remove events for
compile-time type checks and a more concise API.

Implementers

:   -   [AbstractWorker](abstractworker-class)
    -   [AccessibleNode](accessiblenode-class)
    -   [Animation](animation-class)
    -   [ApplicationCache](applicationcache-class)
    -   [AudioNode](../dart-web_audio/audionode-class)
    -   [AudioTrackList](../dart-web_audio/audiotracklist-class)
    -   [BackgroundFetchRegistration](backgroundfetchregistration-class)
    -   [BaseAudioContext](../dart-web_audio/baseaudiocontext-class)
    -   [BatteryManager](batterymanager-class)
    -   [BroadcastChannel](broadcastchannel-class)
    -   [Database](../dart-indexed_db/database-class)
    -   [EventSource](eventsource-class)
    -   [FileReader](filereader-class)
    -   [FileWriter](filewriter-class)
    -   [FontFaceSet](fontfaceset-class)
    -   [GlobalEventHandlers](globaleventhandlers-class)
    -   [HttpRequestEventTarget](httprequesteventtarget-class)
    -   [MediaDevices](mediadevices-class)
    -   [MediaKeySession](mediakeysession-class)
    -   [MediaQueryList](mediaquerylist-class)
    -   [MediaRecorder](mediarecorder-class)
    -   [MediaSource](mediasource-class)
    -   [MediaStream](mediastream-class)
    -   [MediaStreamTrack](mediastreamtrack-class)
    -   [MessagePort](messageport-class)
    -   [MidiAccess](midiaccess-class)
    -   [MidiPort](midiport-class)
    -   [NetworkInformation](networkinformation-class)
    -   [Node](node-class)
    -   [Notification](notification-class)
    -   [OffscreenCanvas](offscreencanvas-class)
    -   [PaymentRequest](paymentrequest-class)
    -   [Performance](performance-class)
    -   [PermissionStatus](permissionstatus-class)
    -   [PresentationAvailability](presentationavailability-class)
    -   [PresentationConnection](presentationconnection-class)
    -   [PresentationConnectionList](presentationconnectionlist-class)
    -   [PresentationRequest](presentationrequest-class)
    -   [RemotePlayback](remoteplayback-class)
    -   [Request](../dart-indexed_db/request-class)
    -   [RtcDataChannel](rtcdatachannel-class)
    -   [RtcDtmfSender](rtcdtmfsender-class)
    -   [RtcPeerConnection](rtcpeerconnection-class)
    -   [ScreenOrientation](screenorientation-class)
    -   [Sensor](sensor-class)
    -   [ServiceWorker](serviceworker-class)
    -   [ServiceWorkerContainer](serviceworkercontainer-class)
    -   [ServiceWorkerRegistration](serviceworkerregistration-class)
    -   [SharedWorker](sharedworker-class)
    -   [SourceBuffer](sourcebuffer-class)
    -   [SourceBufferList](sourcebufferlist-class)
    -   [SpeechRecognition](speechrecognition-class)
    -   [SpeechSynthesis](speechsynthesis-class)
    -   [SpeechSynthesisUtterance](speechsynthesisutterance-class)
    -   [TextTrack](texttrack-class)
    -   [TextTrackCue](texttrackcue-class)
    -   [TextTrackList](texttracklist-class)
    -   [Transaction](../dart-indexed_db/transaction-class)
    -   [VideoTrackList](videotracklist-class)
    -   [VisualViewport](visualviewport-class)
    -   [VR](vr-class)
    -   [VRDevice](vrdevice-class)
    -   [VRDisplay](vrdisplay-class)
    -   [VRSession](vrsession-class)
    -   [WebSocket](websocket-class)
    -   [Window](window-class)
    -   [WindowBase](windowbase-class)
    -   [WindowEventHandlers](windoweventhandlers-class)
    -   [Worker](worker-class)
    -   [WorkerGlobalScope](workerglobalscope-class)
    -   [WorkerPerformance](workerperformance-class)

Annotations

:   -   \@Native(\"EventTarget\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

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

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

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
<https://api.dart.dev/stable/2.18.5/dart-html/EventTarget-class.html>
:::
