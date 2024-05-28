[dart:html](../../dart-html/dart-html-library){._links-link}

SpeechSynthesisUtterance constructor
====================================

::: {.section .multi-line-signature}
SpeechSynthesisUtterance(

1.  \[[String](../../dart-core/string-class)? text\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SpeechSynthesisUtterance([String? text]) {
  if (text != null) {
    return SpeechSynthesisUtterance._create_1(text);
  }
  return SpeechSynthesisUtterance._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechSynthesisUtterance/SpeechSynthesisUtterance.html>
:::
