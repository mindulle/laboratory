[dart:html](../../dart-html/dart-html-library){._links-link}

SpeechRecognitionEvent constructor
==================================

::: {.section .multi-line-signature}
SpeechRecognitionEvent(

1.  [String](../../dart-core/string-class) type,
2.  \[[Map](../../dart-core/map-class)? initDict\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SpeechRecognitionEvent(String type, [Map? initDict]) {
  if (initDict != null) {
    var initDict_1 = convertDartToNative_Dictionary(initDict);
    return SpeechRecognitionEvent._create_1(type, initDict_1);
  }
  return SpeechRecognitionEvent._create_2(type);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognitionEvent/SpeechRecognitionEvent.html>
:::
