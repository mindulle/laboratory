[dart:html](../../dart-html/dart-html-library){._links-link}

resultEvent constant
====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[SpeechRecognitionEvent](../speechrecognitionevent-class)\>
const resultEvent
:::

Static factory designed to expose `result` events to event handlers that
are not necessarily instances of
[SpeechRecognition](../speechrecognition-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<SpeechRecognitionEvent> resultEvent =
    const EventStreamProvider<SpeechRecognitionEvent>('result');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/resultEvent-constant.html>
:::
