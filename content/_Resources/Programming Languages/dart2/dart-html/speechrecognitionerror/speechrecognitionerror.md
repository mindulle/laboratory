[dart:html](../../dart-html/dart-html-library){._links-link}

SpeechRecognitionError constructor
==================================

::: {.section .multi-line-signature}
SpeechRecognitionError(

1.  [String](../../dart-core/string-class) type,
2.  \[[Map](../../dart-core/map-class)? initDict\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SpeechRecognitionError(String type, [Map? initDict]) {
  if (initDict != null) {
    var initDict_1 = convertDartToNative_Dictionary(initDict);
    return SpeechRecognitionError._create_1(type, initDict_1);
  }
  return SpeechRecognitionError._create_2(type);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognitionError/SpeechRecognitionError.html>
:::
