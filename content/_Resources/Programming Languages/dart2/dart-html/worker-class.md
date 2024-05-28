[dart:html](../dart-html/dart-html-library){._links-link}

Worker class
============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   Worker

Implemented types

:   -   [AbstractWorker](abstractworker-class)

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@SupportedBrowser(SupportedBrowser.IE, \'10\')
    -   \@SupportedBrowser(SupportedBrowser.SAFARI)
    -   \@Native(\"Worker\")

Constructors
------------

[Worker](worker/worker)([String](../dart-core/string-class) scriptUrl)

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

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onError](worker/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `error` events handled by this [Worker](worker-class).

[onMessage](worker/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only
:::

Stream of `message` events handled by this [Worker](worker-class).

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

[postMessage](worker/postmessage)(dynamic message,
\[[List](../dart-core/list-class)\<[Object](../dart-core/object-class)\>?
transfer\]) → void

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[terminate](worker/terminate)() → void

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

[supported](worker/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Constants
---------

[errorEvent](worker/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of [Worker](worker-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[messageEvent](worker/messageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>
:   Static factory designed to expose `message` events to event handlers
    that are not necessarily instances of [Worker](worker-class).
    <div>

    `const EventStreamProvider<MessageEvent>('message')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Worker-class.html>
:::
