[dart:html](../dart-html/dart-html-library){._links-link}

RtcDataChannel class
====================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   RtcDataChannel

Annotations

:   -   \@Native(\"RTCDataChannel,DataChannel\")

Properties {#instance-properties}
----------

[binaryType](rtcdatachannel/binarytype) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[bufferedAmount](rtcdatachannel/bufferedamount) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[bufferedAmountLowThreshold](rtcdatachannel/bufferedamountlowthreshold)
↔ [int](../dart-core/int-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](rtcdatachannel/id) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[label](rtcdatachannel/label) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[maxRetransmits](rtcdatachannel/maxretransmits) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[maxRetransmitTime](rtcdatachannel/maxretransmittime) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[negotiated](rtcdatachannel/negotiated) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onClose](rtcdatachannel/onclose) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `close` events handled by this
[RtcDataChannel](rtcdatachannel-class).

[onError](rtcdatachannel/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this
[RtcDataChannel](rtcdatachannel-class).

[onMessage](rtcdatachannel/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only
:::

Stream of `message` events handled by this
[RtcDataChannel](rtcdatachannel-class).

[onOpen](rtcdatachannel/onopen) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `open` events handled by this
[RtcDataChannel](rtcdatachannel-class).

[ordered](rtcdatachannel/ordered) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[protocol](rtcdatachannel/protocol) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[readyState](rtcdatachannel/readystate) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[reliable](rtcdatachannel/reliable) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

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

::: {.features}
inherited
:::

[close](rtcdatachannel/close)() → void

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

[send](rtcdatachannel/send)(dynamic data) → void

[sendBlob](rtcdatachannel/sendblob)([Blob](blob-class) data) → void

::: {.features}
\@JSName(\'send\')
:::

[sendByteBuffer](rtcdatachannel/sendbytebuffer)([ByteBuffer](../dart-typed_data/bytebuffer-class)
data) → void

::: {.features}
\@JSName(\'send\')
:::

[sendString](rtcdatachannel/sendstring)([String](../dart-core/string-class)
data) → void

::: {.features}
\@JSName(\'send\')
:::

[sendTypedData](rtcdatachannel/sendtypeddata)([TypedData](../dart-typed_data/typeddata-class)
data) → void

::: {.features}
\@JSName(\'send\')
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

[closeEvent](rtcdatachannel/closeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `close` events to event handlers
    that are not necessarily instances of
    [RtcDataChannel](rtcdatachannel-class).
    <div>

    `const EventStreamProvider<Event>('close')`

    </div>

[errorEvent](rtcdatachannel/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [RtcDataChannel](rtcdatachannel-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[messageEvent](rtcdatachannel/messageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>
:   Static factory designed to expose `message` events to event handlers
    that are not necessarily instances of
    [RtcDataChannel](rtcdatachannel-class).
    <div>

    `const EventStreamProvider<MessageEvent>('message')`

    </div>

[openEvent](rtcdatachannel/openevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `open` events to event handlers
    that are not necessarily instances of
    [RtcDataChannel](rtcdatachannel-class).
    <div>

    `const EventStreamProvider<Event>('open')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcDataChannel-class.html>
:::
