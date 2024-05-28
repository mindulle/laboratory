[dart:html](../../dart-html/dart-html-library){._links-link}

onSoundEnd property
===================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onSoundEnd
:::

Stream of `soundend` events handled by this
[SpeechRecognition](../speechrecognition-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onSoundEnd => soundEndEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/onSoundEnd.html>
:::
