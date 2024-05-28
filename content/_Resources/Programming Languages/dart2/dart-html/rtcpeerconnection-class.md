[dart:html](../dart-html/dart-html-library){._links-link}

RtcPeerConnection class
=======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   RtcPeerConnection

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@Native(\"RTCPeerConnection,webkitRTCPeerConnection,mozRTCPeerConnection\")

Constructors
------------

[RtcPeerConnection](rtcpeerconnection/rtcpeerconnection)([Map](../dart-core/map-class)
rtcIceServers, \[[Map](../dart-core/map-class)? mediaConstraints\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[connectionState](rtcpeerconnection/connectionstate) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[iceConnectionState](rtcpeerconnection/iceconnectionstate) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[iceGatheringState](rtcpeerconnection/icegatheringstate) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[localDescription](rtcpeerconnection/localdescription) →
[RtcSessionDescription](rtcsessiondescription-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAddStream](rtcpeerconnection/onaddstream) →
[Stream](../dart-async/stream-class)\<[MediaStreamEvent](mediastreamevent-class)\>

::: {.features}
read-only
:::

Stream of `addstream` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onConnectionStateChange](rtcpeerconnection/onconnectionstatechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `connectionstatechange` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onDataChannel](rtcpeerconnection/ondatachannel) →
[Stream](../dart-async/stream-class)\<[RtcDataChannelEvent](rtcdatachannelevent-class)\>

::: {.features}
read-only
:::

Stream of `datachannel` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onIceCandidate](rtcpeerconnection/onicecandidate) →
[Stream](../dart-async/stream-class)\<[RtcPeerConnectionIceEvent](rtcpeerconnectioniceevent-class)\>

::: {.features}
read-only
:::

Stream of `icecandidate` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onIceConnectionStateChange](rtcpeerconnection/oniceconnectionstatechange)
→ [Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `iceconnectionstatechange` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onNegotiationNeeded](rtcpeerconnection/onnegotiationneeded) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `negotiationneeded` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onRemoveStream](rtcpeerconnection/onremovestream) →
[Stream](../dart-async/stream-class)\<[MediaStreamEvent](mediastreamevent-class)\>

::: {.features}
read-only
:::

Stream of `removestream` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onSignalingStateChange](rtcpeerconnection/onsignalingstatechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `signalingstatechange` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[onTrack](rtcpeerconnection/ontrack) →
[Stream](../dart-async/stream-class)\<[RtcTrackEvent](rtctrackevent-class)\>

::: {.features}
read-only
:::

Stream of `track` events handled by this
[RtcPeerConnection](rtcpeerconnection-class).

[remoteDescription](rtcpeerconnection/remotedescription) →
[RtcSessionDescription](rtcsessiondescription-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[signalingState](rtcpeerconnection/signalingstate) →
[String](../dart-core/string-class)?

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

[addIceCandidate](rtcpeerconnection/addicecandidate)([Object](../dart-core/object-class)
candidate, \[[VoidCallback](voidcallback)? successCallback,
[RtcPeerConnectionErrorCallback](rtcpeerconnectionerrorcallback)?
failureCallback\]) → [Future](../dart-async/future-class)

[addStream](rtcpeerconnection/addstream)([MediaStream](mediastream-class)?
stream, \[[Map](../dart-core/map-class)? mediaConstraints\]) → void

[addTrack](rtcpeerconnection/addtrack)([MediaStreamTrack](mediastreamtrack-class)
track, [MediaStream](mediastream-class) streams) →
[RtcRtpSender](rtcrtpsender-class)

[close](rtcpeerconnection/close)() → void

[createAnswer](rtcpeerconnection/createanswer)(\[[Map](../dart-core/map-class)?
options\]) →
[Future](../dart-async/future-class)\<[RtcSessionDescription](rtcsessiondescription-class)\>

[createDataChannel](rtcpeerconnection/createdatachannel)([String](../dart-core/string-class)
label, \[[Map](../dart-core/map-class)? dataChannelDict\]) →
[RtcDataChannel](rtcdatachannel-class)

[createDtmfSender](rtcpeerconnection/createdtmfsender)([MediaStreamTrack](mediastreamtrack-class)
track) → [RtcDtmfSender](rtcdtmfsender-class)

::: {.features}
\@JSName(\'createDTMFSender\')
:::

[createOffer](rtcpeerconnection/createoffer)(\[[Map](../dart-core/map-class)?
options\]) →
[Future](../dart-async/future-class)\<[RtcSessionDescription](rtcsessiondescription-class)\>

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getLegacyStats](rtcpeerconnection/getlegacystats)(\[[MediaStreamTrack](mediastreamtrack-class)?
selector\]) →
[Future](../dart-async/future-class)\<[RtcStatsResponse](rtcstatsresponse-class)\>

Temporarily exposes \_getStats and old getStats as getLegacyStats until
Chrome fully supports new getStats API.

[getLocalStreams](rtcpeerconnection/getlocalstreams)() →
[List](../dart-core/list-class)\<[MediaStream](mediastream-class)\>

[getReceivers](rtcpeerconnection/getreceivers)() →
[List](../dart-core/list-class)\<[RtcRtpReceiver](rtcrtpreceiver-class)\>

[getRemoteStreams](rtcpeerconnection/getremotestreams)() →
[List](../dart-core/list-class)\<[MediaStream](mediastream-class)\>

[getSenders](rtcpeerconnection/getsenders)() →
[List](../dart-core/list-class)\<[RtcRtpSender](rtcrtpsender-class)\>

[getStats](rtcpeerconnection/getstats)() →
[Future](../dart-async/future-class)\<[RtcStatsReport](rtcstatsreport-class)\>

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

[removeStream](rtcpeerconnection/removestream)([MediaStream](mediastream-class)?
stream) → void

[removeTrack](rtcpeerconnection/removetrack)([RtcRtpSender](rtcrtpsender-class)
sender) → void

[setConfiguration](rtcpeerconnection/setconfiguration)([Map](../dart-core/map-class)
configuration) → void

[setLocalDescription](rtcpeerconnection/setlocaldescription)([Map](../dart-core/map-class)
description) → [Future](../dart-async/future-class)

[setRemoteDescription](rtcpeerconnection/setremotedescription)([Map](../dart-core/map-class)
description) → [Future](../dart-async/future-class)

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

[supported](rtcpeerconnection/supported) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if Real Time Communication (RTC) APIs are supported and enabled
on the current platform.

Static Methods
--------------

[generateCertificate](rtcpeerconnection/generatecertificate)(dynamic
keygenAlgorithm) → [Future](../dart-async/future-class)

Constants
---------

[addStreamEvent](rtcpeerconnection/addstreamevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MediaStreamEvent](mediastreamevent-class)\>
:   Static factory designed to expose `addstream` events to event
    handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<MediaStreamEvent>('addstream')`

    </div>

[connectionStateChangeEvent](rtcpeerconnection/connectionstatechangeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `connectionstatechange` events to
    event handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<Event>('connectionstatechange')`

    </div>

[dataChannelEvent](rtcpeerconnection/datachannelevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[RtcDataChannelEvent](rtcdatachannelevent-class)\>
:   Static factory designed to expose `datachannel` events to event
    handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<RtcDataChannelEvent>('datachannel')`

    </div>

[iceCandidateEvent](rtcpeerconnection/icecandidateevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[RtcPeerConnectionIceEvent](rtcpeerconnectioniceevent-class)\>
:   Static factory designed to expose `icecandidate` events to event
    handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<RtcPeerConnectionIceEvent>('icecandidate')`

    </div>

[iceConnectionStateChangeEvent](rtcpeerconnection/iceconnectionstatechangeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `iceconnectionstatechange` events
    to event handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<Event>('iceconnectionstatechange')`

    </div>

[negotiationNeededEvent](rtcpeerconnection/negotiationneededevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `negotiationneeded` events to
    event handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<Event>('negotiationneeded')`

    </div>

[removeStreamEvent](rtcpeerconnection/removestreamevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MediaStreamEvent](mediastreamevent-class)\>
:   Static factory designed to expose `removestream` events to event
    handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<MediaStreamEvent>('removestream')`

    </div>

[signalingStateChangeEvent](rtcpeerconnection/signalingstatechangeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `signalingstatechange` events to
    event handlers that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<Event>('signalingstatechange')`

    </div>

[trackEvent](rtcpeerconnection/trackevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[RtcTrackEvent](rtctrackevent-class)\>
:   Static factory designed to expose `track` events to event handlers
    that are not necessarily instances of
    [RtcPeerConnection](rtcpeerconnection-class).
    <div>

    `const EventStreamProvider<RtcTrackEvent>('track')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection-class.html>
:::
