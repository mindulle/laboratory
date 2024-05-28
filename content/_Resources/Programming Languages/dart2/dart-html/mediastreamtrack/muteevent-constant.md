[dart:html](../../dart-html/dart-html-library){._links-link}

muteEvent constant
==================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const muteEvent
:::

Static factory designed to expose `mute` events to event handlers that
are not necessarily instances of
[MediaStreamTrack](../mediastreamtrack-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> muteEvent =
    const EventStreamProvider<Event>('mute');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStreamTrack/muteEvent-constant.html>
:::
