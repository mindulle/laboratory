[dart:html](../dart-html/dart-html-library){._links-link}

DedicatedWorkerGlobalScope class
================================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [WorkerGlobalScope](workerglobalscope-class)
    -   DedicatedWorkerGlobalScope

Annotations

:   -   \@Native(\"DedicatedWorkerGlobalScope\")

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

[onError](workerglobalscope/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `error` events handled by this
[WorkerGlobalScope](workerglobalscope-class).

[onMessage](dedicatedworkerglobalscope/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only
:::

Stream of `message` events handled by this
[DedicatedWorkerGlobalScope](dedicatedworkerglobalscope-class).

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

[close](dedicatedworkerglobalscope/close)() → void

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

[postMessage](dedicatedworkerglobalscope/postmessage)(dynamic message,
\[[List](../dart-core/list-class)\<[Object](../dart-core/object-class)\>?
transfer\]) → void

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[requestFileSystemSync](dedicatedworkerglobalscope/requestfilesystemsync)([int](../dart-core/int-class)
type, [int](../dart-core/int-class) size) → \_DOMFileSystemSync

::: {.features}
\@JSName(\'webkitRequestFileSystemSync\'),
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

[resolveLocalFileSystemSyncUrl](dedicatedworkerglobalscope/resolvelocalfilesystemsyncurl)([String](../dart-core/string-class)
url) → \_EntrySync

::: {.features}
\@JSName(\'webkitResolveLocalFileSystemSyncURL\'),
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
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

[instance](dedicatedworkerglobalscope/instance) →
[DedicatedWorkerGlobalScope](dedicatedworkerglobalscope-class)

::: {.features}
read-only, override
:::

Constants
---------

[messageEvent](dedicatedworkerglobalscope/messageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>
:   Static factory designed to expose `message` events to event handlers
    that are not necessarily instances of
    [DedicatedWorkerGlobalScope](dedicatedworkerglobalscope-class).
    <div>

    `const EventStreamProvider<MessageEvent>('message')`

    </div>

[PERSISTENT](dedicatedworkerglobalscope/persistent-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[TEMPORARY](dedicatedworkerglobalscope/temporary-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DedicatedWorkerGlobalScope-class.html>
:::
