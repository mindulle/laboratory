[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

Request class
=============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](../dart-html/eventtarget-class)
    -   Request

Implementers

:   -   [OpenDBRequest](opendbrequest-class)

Annotations

:   -   \@Unstable()
    -   \@Native(\"IDBRequest\")

Properties {#instance-properties}
----------

[error](request/error) →
[DomException](../dart-html/domexception-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[on](../dart-html/eventtarget/on) → [Events](../dart-html/events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onError](request/onerror) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this [Request](request-class).

[onSuccess](request/onsuccess) →
[Stream](../dart-async/stream-class)\<[Event](../dart-html/event-class)\>

::: {.features}
read-only
:::

Stream of `success` events handled by this [Request](request-class).

[readyState](request/readystate) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[result](request/result) → dynamic

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[source](request/source) → [Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'Null\'), read-only
:::

[transaction](request/transaction) → [Transaction](transaction-class)?

::: {.features}
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

[errorEvent](request/errorevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of [Request](request-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[successEvent](request/successevent-constant) → const [EventStreamProvider](../dart-html/eventstreamprovider-class)\<[Event](../dart-html/event-class)\>
:   Static factory designed to expose `success` events to event handlers
    that are not necessarily instances of [Request](request-class).
    <div>

    `const EventStreamProvider<Event>('success')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Request-class.html>
:::
