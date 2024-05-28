[dart:html](../../dart-html/dart-html-library){._links-link}

unloadEvent constant
====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const unloadEvent
:::

Static factory designed to expose `unload` events to event handlers that
are not necessarily instances of [BodyElement](../bodyelement-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> unloadEvent =
    const EventStreamProvider<Event>('unload');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BodyElement/unloadEvent-constant.html>
:::
