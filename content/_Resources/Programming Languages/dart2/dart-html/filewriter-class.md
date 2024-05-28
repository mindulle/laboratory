[dart:html](../dart-html/dart-html-library){._links-link}

FileWriter class
================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   FileWriter

Annotations

:   -   \@Native(\"FileWriter\")

Properties {#instance-properties}
----------

[error](filewriter/error) → [DomException](domexception-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[length](filewriter/length) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](filewriter/onabort) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `abort` events handled by this [FileWriter](filewriter-class).

[onError](filewriter/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this [FileWriter](filewriter-class).

[onProgress](filewriter/onprogress) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `progress` events handled by this
[FileWriter](filewriter-class).

[onWrite](filewriter/onwrite) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `write` events handled by this [FileWriter](filewriter-class).

[onWriteEnd](filewriter/onwriteend) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `writeend` events handled by this
[FileWriter](filewriter-class).

[onWriteStart](filewriter/onwritestart) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `writestart` events handled by this
[FileWriter](filewriter-class).

[position](filewriter/position) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[readyState](filewriter/readystate) → [int](../dart-core/int-class)?

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

[abort](filewriter/abort)() → void

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

[seek](filewriter/seek)([int](../dart-core/int-class) position) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[truncate](filewriter/truncate)([int](../dart-core/int-class) size) →
void

[write](filewriter/write)([Blob](blob-class) data) → void

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

[abortEvent](filewriter/abortevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `abort` events to event handlers
    that are not necessarily instances of
    [FileWriter](filewriter-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('abort')`

    </div>

[DONE](filewriter/done-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[errorEvent](filewriter/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [FileWriter](filewriter-class).
    <div>

    `const EventStreamProvider<Event>('error')`

    </div>

[INIT](filewriter/init-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

[progressEvent](filewriter/progressevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `progress` events to event
    handlers that are not necessarily instances of
    [FileWriter](filewriter-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('progress')`

    </div>

[writeEndEvent](filewriter/writeendevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `writeend` events to event
    handlers that are not necessarily instances of
    [FileWriter](filewriter-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('writeend')`

    </div>

[writeEvent](filewriter/writeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `write` events to event handlers
    that are not necessarily instances of
    [FileWriter](filewriter-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('write')`

    </div>

[writeStartEvent](filewriter/writestartevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `writestart` events to event
    handlers that are not necessarily instances of
    [FileWriter](filewriter-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('writestart')`

    </div>

[WRITING](filewriter/writing-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileWriter-class.html>
:::
