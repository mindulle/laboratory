[dart:html](../../dart-html/dart-html-library){._links-link}

audioStartEvent constant
========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const audioStartEvent
:::

Static factory designed to expose `audiostart` events to event handlers
that are not necessarily instances of
[SpeechRecognition](../speechrecognition-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> audioStartEvent =
    const EventStreamProvider<Event>('audiostart');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/audioStartEvent-constant.html>
:::
