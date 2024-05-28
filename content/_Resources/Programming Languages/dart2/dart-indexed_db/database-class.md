[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

Database class
==============

An indexed database object for storing client-side data in web apps.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](../dart-html/eventtarget-class)
    -   Database

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX, \'15\')
    -   \@SupportedBrowser(SupportedBrowser.IE, \'10\')
    -   \@Unstable()
    -   \@Native(\"IDBDatabase\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[name](database/name) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[objectStoreNames](database/objectstorenames) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

::: {.features}
\@Returns(\'DomStringList\'), \@Creates(\'DomStringList\'), read-only
:::

[on](../dart-html/eventtarget/on) → [Events](../dart-html/events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](database/onabort) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `abort` events handled by this [Database](database-class).

[onClose](database/onclose) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `close` events handled by this [Database](database-class).

[onError](database/onerror) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this [Database](database-class).

[onVersionChange](database/onversionchange) →
[Stream](../dart-async/stream-class)\<[VersionChangeEvent](versionchangeevent-class)\>

::: {.features}
read-only
:::

Stream of `versionchange` events handled by this
[Database](database-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[version](database/version) → [int](../dart-core/int-class)?

::: {.features}
\@Creates(\'int\|String\|Null\'), \@Returns(\'int\|String\|Null\'),
read-only
:::

Methods {#instance-methods}
-------

[addEventListener](../dart-html/eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](../dart-html/eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[close](database/close)() → void

[createObjectStore](database/createobjectstore)([String](../dart-core/string-class)
name, {dynamic keyPath, [bool](../dart-core/bool-class)? autoIncrement})
→ [ObjectStore](objectstore-class)

[deleteObjectStore](database/deleteobjectstore)([String](../dart-core/string-class)
name) → void

[dispatchEvent](../dart-html/eventtarget/dispatchevent)([Event](../dart-html/event-class)
event) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](../dart-html/eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](../dart-html/eventlistener)? listener,
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

[transaction](database/transaction)(dynamic storeName\_OR\_storeNames,
[String](../dart-core/string-class) mode) →
[Transaction](transaction-class)

[transactionList](database/transactionlist)([List](../dart-core/list-class)\<[String](../dart-core/string-class)\>
storeNames, [String](../dart-core/string-class) mode) →
[Transaction](transaction-class)

[transactionStore](database/transactionstore)([String](../dart-core/string-class)
storeName, [String](../dart-core/string-class) mode) →
[Transaction](transaction-class)

[transactionStores](database/transactionstores)([DomStringList](../dart-html/domstringlist-class)
storeNames, [String](../dart-core/string-class) mode) →
[Transaction](transaction-class)

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

[abortEvent](database/abortevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `abort` events to event handlers
    that are not necessarily instances of [Database](database-class).
    <div>

    `const EventStreamProvider<Event>('abort')`

    </div>

[closeEvent](database/closeevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `close` events to event handlers
    that are not necessarily instances of [Database](database-class).
    <div>

    `const EventStreamProvider<Event>('close')`

    </div>

[errorEvent](database/errorevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of [Database](database-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[versionChangeEvent](database/versionchangeevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[VersionChangeEvent](versionchangeevent-class)\>
:   Static factory designed to expose `versionchange` events to event
    handlers that are not necessarily instances of
    [Database](database-class).
    <div>

    `const EventStreamProvider<VersionChangeEvent>('versionchange')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database-class.html>
:::
