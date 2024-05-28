[dart:html](../../dart-html/dart-html-library){._links-link}

onSpeechEnd property
====================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onSpeechEnd
:::

Stream of `speechend` events handled by this
[SpeechRecognition](../speechrecognition-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onSpeechEnd => speechEndEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/onSpeechEnd.html>
:::
