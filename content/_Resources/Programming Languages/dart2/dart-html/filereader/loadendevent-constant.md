[dart:html](../../dart-html/dart-html-library){._links-link}

loadEndEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[ProgressEvent](../progressevent-class)\>
const loadEndEvent
:::

Static factory designed to expose `loadend` events to event handlers
that are not necessarily instances of [FileReader](../filereader-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<ProgressEvent> loadEndEvent =
    const EventStreamProvider<ProgressEvent>('loadend');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileReader/loadEndEvent-constant.html>
:::
