[dart:html](../../dart-html/dart-html-library){._links-link}

noMatchEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[SpeechRecognitionEvent](../speechrecognitionevent-class)\>
const noMatchEvent
:::

Static factory designed to expose `nomatch` events to event handlers
that are not necessarily instances of
[SpeechRecognition](../speechrecognition-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<SpeechRecognitionEvent> noMatchEvent =
    const EventStreamProvider<SpeechRecognitionEvent>('nomatch');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/noMatchEvent-constant.html>
:::
