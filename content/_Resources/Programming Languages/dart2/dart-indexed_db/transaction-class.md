[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

Transaction class
=================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](../dart-html/eventtarget-class)
    -   Transaction

Annotations

:   -   \@Unstable()
    -   \@Native(\"IDBTransaction\")

Properties {#instance-properties}
----------

[completed](transaction/completed) →
[Future](../dart-async/future-class)\<[Database](database-class)\>

::: {.features}
read-only
:::

Provides a Future which will be completed once the transaction has
completed.

[db](transaction/db) → [Database](database-class)?

::: {.features}
read-only
:::

[error](transaction/error) →
[DomException](../dart-html/domexception-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[mode](transaction/mode) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[objectStoreNames](transaction/objectstorenames) →
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

[onAbort](transaction/onabort) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `abort` events handled by this
[Transaction](transaction-class).

[onComplete](transaction/oncomplete) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `complete` events handled by this
[Transaction](transaction-class).

[onError](transaction/onerror) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this
[Transaction](transaction-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[abort](transaction/abort)() → void

[addEventListener](../dart-html/eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](../dart-html/eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

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

[objectStore](transaction/objectstore)([String](../dart-core/string-class)
name) → [ObjectStore](objectstore-class)

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

[abortEvent](transaction/abortevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `abort` events to event handlers
    that are not necessarily instances of
    [Transaction](transaction-class).
    <div>

    `const EventStreamProvider<Event>('abort')`

    </div>

[completeEvent](transaction/completeevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `complete` events to event
    handlers that are not necessarily instances of
    [Transaction](transaction-class).
    <div>

    `const EventStreamProvider<Event>('complete')`

    </div>

[errorEvent](transaction/errorevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [Transaction](transaction-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Transaction-class.html>
:::
