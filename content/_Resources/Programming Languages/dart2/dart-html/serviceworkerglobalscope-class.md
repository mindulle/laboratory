[dart:html](../dart-html/dart-html-library){._links-link}

ServiceWorkerGlobalScope class
==============================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [WorkerGlobalScope](workerglobalscope-class)
    -   ServiceWorkerGlobalScope

Annotations

:   -   \@Native(\"ServiceWorkerGlobalScope\")

Properties {#instance-properties}
----------

[addressSpace](workerglobalscope/addressspace) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[caches](workerglobalscope/caches) → [CacheStorage](cachestorage-class)?

::: {.features}
read-only, inherited
:::

[clients](serviceworkerglobalscope/clients) → [Clients](clients-class)?

::: {.features}
read-only
:::

[crypto](workerglobalscope/crypto) → [Crypto](crypto-class)?

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[indexedDB](workerglobalscope/indexeddb) →
[IdbFactory](../dart-indexed_db/idbfactory-class)?

::: {.features}
read-only, inherited
:::

[isSecureContext](workerglobalscope/issecurecontext) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[location](workerglobalscope/location) → \_WorkerLocation

::: {.features}
read-only, inherited
:::

[navigator](workerglobalscope/navigator) → \_WorkerNavigator

::: {.features}
read-only, inherited
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onActivate](serviceworkerglobalscope/onactivate) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onError](workerglobalscope/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `error` events handled by this
[WorkerGlobalScope](workerglobalscope-class).

[onFetch](serviceworkerglobalscope/onfetch) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onForeignfetch](serviceworkerglobalscope/onforeignfetch) →
[Stream](../dart-async/stream-class)\<[ForeignFetchEvent](foreignfetchevent-class)\>

::: {.features}
read-only
:::

[onInstall](serviceworkerglobalscope/oninstall) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onMessage](serviceworkerglobalscope/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only
:::

[origin](workerglobalscope/origin) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[performance](workerglobalscope/performance) →
[WorkerPerformance](workerperformance-class)?

::: {.features}
read-only, inherited
:::

[registration](serviceworkerglobalscope/registration) →
[ServiceWorkerRegistration](serviceworkerregistration-class)?

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
read-only, inherited
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
inherited
:::

[btoa](workerglobalscope/btoa)([String](../dart-core/string-class) btoa)
→ [String](../dart-core/string-class)

::: {.features}
inherited
:::

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[fetch](workerglobalscope/fetch)(dynamic input,
\[[Map](../dart-core/map-class)? init\]) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

[importScripts](workerglobalscope/importscripts)([String](../dart-core/string-class)
urls) → void

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

[skipWaiting](serviceworkerglobalscope/skipwaiting)() →
[Future](../dart-async/future-class)

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

[instance](serviceworkerglobalscope/instance) →
[ServiceWorkerGlobalScope](serviceworkerglobalscope-class)

::: {.features}
read-only, override
:::

Constants
---------

[activateEvent](serviceworkerglobalscope/activateevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('activate')`

    </div>

[fetchEvent](serviceworkerglobalscope/fetchevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('fetch')`

    </div>

[foreignfetchEvent](serviceworkerglobalscope/foreignfetchevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ForeignFetchEvent](foreignfetchevent-class)\>

:   <div>

    `const EventStreamProvider<ForeignFetchEvent>('foreignfetch')`

    </div>

[installEvent](serviceworkerglobalscope/installevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('install')`

    </div>

[messageEvent](serviceworkerglobalscope/messageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>

:   <div>

    `const EventStreamProvider<MessageEvent>('message')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ServiceWorkerGlobalScope-class.html>
:::
