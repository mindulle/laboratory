[dart:html](../../dart-html/dart-html-library){._links-link}

soundEndEvent constant
======================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const soundEndEvent
:::

Static factory designed to expose `soundend` events to event handlers
that are not necessarily instances of
[SpeechRecognition](../speechrecognition-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> soundEndEvent =
    const EventStreamProvider<Event>('soundend');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/soundEndEvent-constant.html>
:::
