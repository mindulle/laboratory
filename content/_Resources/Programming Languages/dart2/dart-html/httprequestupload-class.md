[dart:html](../dart-html/dart-html-library){._links-link}

HttpRequestUpload class
=======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [HttpRequestEventTarget](httprequesteventtarget-class)
    -   HttpRequestUpload

Annotations

:   -   \@Native(\"XMLHttpRequestUpload\")

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

[onAbort](httprequesteventtarget/onabort) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `abort` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onError](httprequesteventtarget/onerror) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `error` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onLoad](httprequesteventtarget/onload) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `load` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onLoadEnd](httprequesteventtarget/onloadend) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only, inherited
:::

Stream of `loadend` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onLoadStart](httprequesteventtarget/onloadstart) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `loadstart` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onProgress](httprequesteventtarget/onprogress) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only, inherited
:::

Stream of `progress` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

[onTimeout](httprequesteventtarget/ontimeout) →
[Stream](../dart-async/stream-class)\<[ProgressEvent](progressevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `timeout` events handled by this
[HttpRequestEventTarget](httprequesteventtarget-class).

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequestUpload-class.html>
:::
