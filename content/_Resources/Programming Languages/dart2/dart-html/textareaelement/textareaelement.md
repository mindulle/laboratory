[dart:html](../../dart-html/dart-html-library){._links-link}

TextAreaElement constructor
===========================

::: {.section .multi-line-signature}
TextAreaElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory TextAreaElement() => JS<TextAreaElement>(
    'returns:TextAreaElement;creates:TextAreaElement;new:true',
    '#.createElement(#)',
    document,
    "textarea");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TextAreaElement/TextAreaElement.html>
:::
