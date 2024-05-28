[dart:html](../../dart-html/dart-html-library){._links-link}

loadStartEvent constant
=======================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[ProgressEvent](../progressevent-class)\>
const loadStartEvent
:::

Static factory designed to expose `loadstart` events to event handlers
that are not necessarily instances of [FileReader](../filereader-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<ProgressEvent> loadStartEvent =
    const EventStreamProvider<ProgressEvent>('loadstart');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileReader/loadStartEvent-constant.html>
:::
