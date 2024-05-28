[dart:html](../../dart-html/dart-html-library){._links-link}

copyEvent constant
==================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[ClipboardEvent](../clipboardevent-class)\>
const copyEvent
:::

Static factory designed to expose `copy` events to event handlers that
are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<ClipboardEvent> copyEvent =
    const EventStreamProvider<ClipboardEvent>('copy');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/copyEvent-constant.html>
:::
