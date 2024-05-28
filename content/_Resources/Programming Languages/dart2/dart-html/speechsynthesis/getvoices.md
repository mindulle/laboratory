[dart:html](../../dart-html/dart-html-library){._links-link}

getVoices method
================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[SpeechSynthesisVoice](../speechsynthesisvoice-class)\>
getVoices()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<SpeechSynthesisVoice> getVoices() {
  List<SpeechSynthesisVoice> voices = _getVoices();
  if (voices.length > 0) applyExtension('SpeechSynthesisVoice', voices[0]);
  return voices;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechSynthesis/getVoices.html>
:::
