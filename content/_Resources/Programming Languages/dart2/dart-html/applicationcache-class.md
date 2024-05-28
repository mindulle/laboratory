[dart:html](../dart-html/dart-html-library){._links-link}

ApplicationCache class
======================

ApplicationCache is accessed via
[Window.applicationCache](window/applicationcache).

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   ApplicationCache

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@SupportedBrowser(SupportedBrowser.IE, \'10\')
    -   \@SupportedBrowser(SupportedBrowser.OPERA)
    -   \@SupportedBrowser(SupportedBrowser.SAFARI)
    -   \@Unstable()
    -   \@Native(\"ApplicationCache,DOMApplicationCache,OfflineResourceList\")

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

[onCached](applicationcache/oncached) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `cached` events handled by this
[ApplicationCache](applicationcache-class).

[onChecking](applicationcache/onchecking) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `checking` events handled by this
[ApplicationCache](applicationcache-class).

[onDownloading](applicationcache/ondownloading) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `downloading` events handled by this
[ApplicationCache](applicationcache-class).

[onError](applicationcache/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this
[ApplicationCache](applicationcache-class).

[onNoUpdate](applicationcache/onnoupdate) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `noupdate` events handled by this
[ApplicationCache](applicationcache-class).

[onObsolete](applicationcache/onobsolete) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `obsolete` events handled by this
[ApplicationCache](applicationcache-class).

[onProgress](applicationcache/onprogress) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `progress` events handled by this
[ApplicationCache](applicationcache-class).

[onUpdateReady](applicationcache/onupdateready) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `updateready` events handled by this
[ApplicationCache](applicationcache-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[status](applicationcache/status) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[abort](applicationcache/abort)() → void

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

[swapCache](applicationcache/swapcache)() → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](applicationcache/update)() → void

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

[supported](applicationcache/supported) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Constants
---------

[cachedEvent](applicationcache/cachedevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `cached` events to event handlers
    that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<Event>('cached')`

    </div>

[CHECKING](applicationcache/checking-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[checkingEvent](applicationcache/checkingevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `checking` events to event
    handlers that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<Event>('checking')`

    </div>

[DOWNLOADING](applicationcache/downloading-constant) → const [int](../dart-core/int-class)

:   <div>

    `3`

    </div>

[downloadingEvent](applicationcache/downloadingevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `downloading` events to event
    handlers that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<Event>('downloading')`

    </div>

[errorEvent](applicationcache/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[IDLE](applicationcache/idle-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[noUpdateEvent](applicationcache/noupdateevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `noupdate` events to event
    handlers that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<Event>('noupdate')`

    </div>

[OBSOLETE](applicationcache/obsolete-constant) → const [int](../dart-core/int-class)

:   <div>

    `5`

    </div>

[obsoleteEvent](applicationcache/obsoleteevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `obsolete` events to event
    handlers that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<Event>('obsolete')`

    </div>

[progressEvent](applicationcache/progressevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `progress` events to event
    handlers that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('progress')`

    </div>

[UNCACHED](applicationcache/uncached-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

[UPDATEREADY](applicationcache/updateready-constant) → const [int](../dart-core/int-class)

:   <div>

    `4`

    </div>

[updateReadyEvent](applicationcache/updatereadyevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `updateready` events to event
    handlers that are not necessarily instances of
    [ApplicationCache](applicationcache-class).
    <div>

    `const EventStreamProvider<Event>('updateready')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ApplicationCache-class.html>
:::
