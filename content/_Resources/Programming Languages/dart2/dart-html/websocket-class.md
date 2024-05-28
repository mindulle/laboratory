[dart:html](../dart-html/dart-html-library){._links-link}

WebSocket class
===============

Use the WebSocket interface to connect to a WebSocket, and to send and
receive data on that WebSocket.

To use a WebSocket in your web app, first create a WebSocket object,
passing the WebSocket URL as an argument to the constructor.

``` {.language-dart data-language="dart"}
var webSocket = new WebSocket('ws://127.0.0.1:1337/ws');
```

To send data on the WebSocket, use the [send](websocket/send) method.

``` {.language-dart data-language="dart"}
if (webSocket != null && webSocket.readyState == WebSocket.OPEN) {
  webSocket.send(data);
} else {
  print('WebSocket not connected, message $data not sent');
}
```

To receive data on the WebSocket, register a listener for message
events.

``` {.language-dart data-language="dart"}
webSocket.onMessage.listen((MessageEvent e) {
  receivedData(e.data);
});
```

The message event handler receives a [MessageEvent](messageevent-class)
object as its sole argument. You can also define open, close, and error
handlers, as specified by [Event](event-class)s.

For more information, see the
[WebSockets](http://www.dartlang.org/docs/library-tour/#html-websockets)
section of the library tour and [Introducing
WebSockets](http://www.html5rocks.com/en/tutorials/websockets/basics/),
an HTML5Rocks.com tutorial.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   WebSocket

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@SupportedBrowser(SupportedBrowser.IE, \'10\')
    -   \@SupportedBrowser(SupportedBrowser.SAFARI)
    -   \@Unstable()
    -   \@Native(\"WebSocket\")

Constructors
------------

[WebSocket](websocket/websocket)([String](../dart-core/string-class)
url, \[[Object](../dart-core/object-class)? protocols\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[binaryType](websocket/binarytype) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[bufferedAmount](websocket/bufferedamount) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[extensions](websocket/extensions) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onClose](websocket/onclose) →
[Stream](../dart-async/stream-class)\<[CloseEvent](closeevent-class)\>

::: {.features}
read-only
:::

Stream of `close` events handled by this [WebSocket](websocket-class).

[onError](websocket/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this [WebSocket](websocket-class).

[onMessage](websocket/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only
:::

Stream of `message` events handled by this [WebSocket](websocket-class).

[onOpen](websocket/onopen) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `open` events handled by this [WebSocket](websocket-class).

[protocol](websocket/protocol) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[readyState](websocket/readystate) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[url](websocket/url) → [String](../dart-core/string-class)?

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

[close](websocket/close)(\[[int](../dart-core/int-class)? code,
[String](../dart-core/string-class)? reason\]) → void

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

[send](websocket/send)(dynamic data) → void

Transmit data to the server over this connection.

[sendBlob](websocket/sendblob)([Blob](blob-class) data) → void

::: {.features}
\@JSName(\'send\')
:::

Transmit data to the server over this connection.

[sendByteBuffer](websocket/sendbytebuffer)([ByteBuffer](../dart-typed_data/bytebuffer-class)
data) → void

::: {.features}
\@JSName(\'send\')
:::

Transmit data to the server over this connection.

[sendString](websocket/sendstring)([String](../dart-core/string-class)
data) → void

::: {.features}
\@JSName(\'send\')
:::

Transmit data to the server over this connection.

[sendTypedData](websocket/sendtypeddata)([TypedData](../dart-typed_data/typeddata-class)
data) → void

::: {.features}
\@JSName(\'send\')
:::

Transmit data to the server over this connection.

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

[supported](websocket/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Constants
---------

[CLOSED](websocket/closed-constant) → const [int](../dart-core/int-class)

:   <div>

    `3`

    </div>

[closeEvent](websocket/closeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[CloseEvent](closeevent-class)\>
:   Static factory designed to expose `close` events to event handlers
    that are not necessarily instances of [WebSocket](websocket-class).
    <div>

    `const EventStreamProvider<CloseEvent>('close')`

    </div>

[CLOSING](websocket/closing-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[CONNECTING](websocket/connecting-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

[errorEvent](websocket/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of [WebSocket](websocket-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[messageEvent](websocket/messageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>
:   Static factory designed to expose `message` events to event handlers
    that are not necessarily instances of [WebSocket](websocket-class).
    <div>

    `const EventStreamProvider<MessageEvent>('message')`

    </div>

[OPEN](websocket/open-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[openEvent](websocket/openevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `open` events to event handlers
    that are not necessarily instances of [WebSocket](websocket-class).
    <div>

    `const EventStreamProvider<Event>('open')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WebSocket-class.html>
:::
