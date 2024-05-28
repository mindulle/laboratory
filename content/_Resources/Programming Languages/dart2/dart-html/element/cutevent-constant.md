[dart:html](../../dart-html/dart-html-library){._links-link}

cutEvent constant
=================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[ClipboardEvent](../clipboardevent-class)\>
const cutEvent
:::

Static factory designed to expose `cut` events to event handlers that
are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<ClipboardEvent> cutEvent =
    const EventStreamProvider<ClipboardEvent>('cut');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/cutEvent-constant.html>
:::
