[dart:html](../dart-html/dart-html-library){._links-link}

FileReader class
================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   FileReader

Annotations

:   -   \@Native(\"FileReader\")

Constructors
------------

[FileReader](filereader/filereader)()

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[error](filereader/error) → [DomException](domexception-class)?

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

[onAbort](filereader/onabort) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `abort` events handled by this [FileReader](filereader-class).

[onError](filereader/onerror) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this [FileReader](filereader-class).

[onLoad](filereader/onload) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `load` events handled by this [FileReader](filereader-class).

[onLoadEnd](filereader/onloadend) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `loadend` events handled by this
[FileReader](filereader-class).

[onLoadStart](filereader/onloadstart) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `loadstart` events handled by this
[FileReader](filereader-class).

[onProgress](filereader/onprogress) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only
:::

Stream of `progress` events handled by this
[FileReader](filereader-class).

[readyState](filereader/readystate) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[result](filereader/result) → [Object](../dart-core/object-class)?

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

[abort](filereader/abort)() → void

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

[readAsArrayBuffer](filereader/readasarraybuffer)([Blob](blob-class)
blob) → void

[readAsDataUrl](filereader/readasdataurl)([Blob](blob-class) blob) →
void

::: {.features}
\@JSName(\'readAsDataURL\')
:::

[readAsText](filereader/readastext)([Blob](blob-class) blob,
\[[String](../dart-core/string-class)? label\]) → void

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

[abortEvent](filereader/abortevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `abort` events to event handlers
    that are not necessarily instances of
    [FileReader](filereader-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('abort')`

    </div>

[DONE](filereader/done-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[EMPTY](filereader/empty-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

[errorEvent](filereader/errorevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `error` events to event handlers
    that are not necessarily instances of
    [FileReader](filereader-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('error')`

    </div>

[loadEndEvent](filereader/loadendevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `loadend` events to event handlers
    that are not necessarily instances of
    [FileReader](filereader-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('loadend')`

    </div>

[loadEvent](filereader/loadevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `load` events to event handlers
    that are not necessarily instances of
    [FileReader](filereader-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('load')`

    </div>

[LOADING](filereader/loading-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[loadStartEvent](filereader/loadstartevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `loadstart` events to event
    handlers that are not necessarily instances of
    [FileReader](filereader-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('loadstart')`

    </div>

[progressEvent](filereader/progressevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[ProgressEvent](progressevent-class)\>
:   Static factory designed to expose `progress` events to event
    handlers that are not necessarily instances of
    [FileReader](filereader-class).
    <div>

    `const EventStreamProvider<ProgressEvent>('progress')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileReader-class.html>
:::
