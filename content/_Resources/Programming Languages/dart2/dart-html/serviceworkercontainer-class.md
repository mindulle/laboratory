[dart:html](../dart-html/dart-html-library){._links-link}

ServiceWorkerContainer class
============================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   ServiceWorkerContainer

Annotations

:   -   \@Native(\"ServiceWorkerContainer\")

Properties {#instance-properties}
----------

[controller](serviceworkercontainer/controller) →
[ServiceWorker](serviceworker-class)?

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

[onMessage](serviceworkercontainer/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only
:::

[ready](serviceworkercontainer/ready) →
[Future](../dart-async/future-class)\<[ServiceWorkerRegistration](serviceworkerregistration-class)\>

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

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getRegistration](serviceworkercontainer/getregistration)(\[[String](../dart-core/string-class)?
documentURL\]) →
[Future](../dart-async/future-class)\<[ServiceWorkerRegistration](serviceworkerregistration-class)\>

[getRegistrations](serviceworkercontainer/getregistrations)() →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\>

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[register](serviceworkercontainer/register)([String](../dart-core/string-class)
url, \[[Map](../dart-core/map-class)? options\]) →
[Future](../dart-async/future-class)\<[ServiceWorkerRegistration](serviceworkerregistration-class)\>

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

[messageEvent](serviceworkercontainer/messageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>

:   <div>

    `const EventStreamProvider<MessageEvent>('message')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ServiceWorkerContainer-class.html>
:::
