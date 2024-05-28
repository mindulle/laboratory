[dart:html](../../dart-html/dart-html-library){._links-link}

selectionChangeEvent constant
=============================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const selectionChangeEvent
:::

Static factory designed to expose `selectionchange` events to event
handlers that are not necessarily instances of
[Document](../document-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> selectionChangeEvent =
    const EventStreamProvider<Event>('selectionchange');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/selectionChangeEvent-constant.html>
:::
