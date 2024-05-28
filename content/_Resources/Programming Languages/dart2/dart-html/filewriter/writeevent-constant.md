[dart:html](../../dart-html/dart-html-library){._links-link}

writeEvent constant
===================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[ProgressEvent](../progressevent-class)\>
const writeEvent
:::

Static factory designed to expose `write` events to event handlers that
are not necessarily instances of [FileWriter](../filewriter-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<ProgressEvent> writeEvent =
    const EventStreamProvider<ProgressEvent>('write');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileWriter/writeEvent-constant.html>
:::
