[dart:html](../../dart-html/dart-html-library){._links-link}

loadEvent constant
==================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[ProgressEvent](../progressevent-class)\>
const loadEvent
:::

Static factory designed to expose `load` events to event handlers that
are not necessarily instances of
[HttpRequestEventTarget](../httprequesteventtarget-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<ProgressEvent> loadEvent =
    const EventStreamProvider<ProgressEvent>('load');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequestEventTarget/loadEvent-constant.html>
:::
