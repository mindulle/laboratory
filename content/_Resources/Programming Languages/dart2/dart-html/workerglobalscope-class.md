[dart:html](../dart-html/dart-html-library){._links-link}

WorkerGlobalScope class
=======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   WorkerGlobalScope

Implemented types

:   -   [WindowBase64](windowbase64-class)

Implementers

:   -   [DedicatedWorkerGlobalScope](dedicatedworkerglobalscope-class)
    -   [ServiceWorkerGlobalScope](serviceworkerglobalscope-class)
    -   [SharedWorkerGlobalScope](sharedworkerglobalscope-class)

Annotations

:   -   \@Native(\"WorkerGlobalScope\")

Properties {#instance-properties}
----------

[addressSpace](workerglobalscope/addressspace) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[caches](workerglobalscope/caches) → [CacheStorage](cachestorage-class)?

::: {.features}
read-only
:::

[crypto](workerglobalscope/crypto) → [Crypto](crypto-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[indexedDB](workerglobalscope/indexeddb) →
[IdbFactory](../dart-indexed_db/idbfactory-class)?

::: {.features}
read-only
:::

[isSecureContext](workerglobalscope/issecurecontext) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[location](workerglobalscope/location) → \_WorkerLocation

::: {.features}
read-only
:::

[navigator](workerglobalscope/navigator) → \_WorkerNavigator

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onError](workerglobalscope/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this
[WorkerGlobalScope](workerglobalscope-class).

[origin](workerglobalscope/origin) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[performance](workerglobalscope/performance) →
[WorkerPerformance](workerperformance-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[self](workerglobalscope/self) →
[WorkerGlobalScope](workerglobalscope-class)

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

[atob](workerglobalscope/atob)([String](../dart-core/string-class) atob)
→ [String](../dart-core/string-class)

::: {.features}
override
:::

[btoa](workerglobalscope/btoa)([String](../dart-core/string-class) btoa)
→ [String](../dart-core/string-class)

::: {.features}
override
:::

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[fetch](workerglobalscope/fetch)(dynamic input,
\[[Map](../dart-core/map-class)? init\]) →
[Future](../dart-async/future-class)

[importScripts](workerglobalscope/importscripts)([String](../dart-core/string-class)
urls) → void

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

Static Properties
-----------------

[instance](workerglobalscope/instance) →
[WorkerGlobalScope](workerglobalscope-class)

::: {.features}
read-only
:::

Constants
---------

[errorEvent](workerglobalscope/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [WorkerGlobalScope](workerglobalscope-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WorkerGlobalScope-class.html>
:::
