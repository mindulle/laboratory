[dart:html](../../dart-html/dart-html-library){._links-link}

enterEvent constant
===================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const enterEvent
:::

Static factory designed to expose `enter` events to event handlers that
are not necessarily instances of [TextTrackCue](../texttrackcue-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> enterEvent =
    const EventStreamProvider<Event>('enter');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TextTrackCue/enterEvent-constant.html>
:::
