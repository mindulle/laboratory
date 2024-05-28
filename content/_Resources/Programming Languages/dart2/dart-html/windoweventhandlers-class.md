[dart:html](../dart-html/dart-html-library){._links-link}

WindowEventHandlers class
=========================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   WindowEventHandlers

Implementers

:   -   [BodyElement](bodyelement-class)
    -   [Window](window-class)

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

[onHashChange](windoweventhandlers/onhashchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onMessage](windoweventhandlers/onmessage) →
[Stream](../dart-async/stream-class)\<[MessageEvent](messageevent-class)\>

::: {.features}
read-only
:::

[onOffline](windoweventhandlers/onoffline) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onOnline](windoweventhandlers/ononline) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onPopState](windoweventhandlers/onpopstate) →
[Stream](../dart-async/stream-class)\<[PopStateEvent](popstateevent-class)\>

::: {.features}
read-only
:::

[onStorage](windoweventhandlers/onstorage) →
[Stream](../dart-async/stream-class)\<[StorageEvent](storageevent-class)\>

::: {.features}
read-only
:::

[onUnload](windoweventhandlers/onunload) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

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

Constants
---------

[hashChangeEvent](windoweventhandlers/hashchangeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('hashchange')`

    </div>

[messageEvent](windoweventhandlers/messageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[MessageEvent](messageevent-class)\>

:   <div>

    `const EventStreamProvider<MessageEvent>('message')`

    </div>

[offlineEvent](windoweventhandlers/offlineevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('offline')`

    </div>

[onlineEvent](windoweventhandlers/onlineevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('online')`

    </div>

[popStateEvent](windoweventhandlers/popstateevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[PopStateEvent](popstateevent-class)\>

:   <div>

    `const EventStreamProvider<PopStateEvent>('popstate')`

    </div>

[storageEvent](windoweventhandlers/storageevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[StorageEvent](storageevent-class)\>

:   <div>

    `const EventStreamProvider<StorageEvent>('storage')`

    </div>

[unloadEvent](windoweventhandlers/unloadevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('unload')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WindowEventHandlers-class.html>
:::
