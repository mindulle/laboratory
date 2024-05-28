[dart:html](../../dart-html/dart-html-library){._links-link}

resizeEvent constant
====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const resizeEvent
:::

Static factory designed to expose `resize` events to event handlers that
are not necessarily instances of [BodyElement](../bodyelement-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> resizeEvent =
    const EventStreamProvider<Event>('resize');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BodyElement/resizeEvent-constant.html>
:::
