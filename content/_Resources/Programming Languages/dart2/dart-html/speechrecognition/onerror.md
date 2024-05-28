[dart:html](../../dart-html/dart-html-library){._links-link}

onError property
================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[SpeechRecognitionError](../speechrecognitionerror-class)\>
onError
:::

Stream of `error` events handled by this
[SpeechRecognition](../speechrecognition-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<SpeechRecognitionError> get onError => errorEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/onError.html>
:::
