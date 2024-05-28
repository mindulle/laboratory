[dart:html](../../dart-html/dart-html-library){._links-link}

ButtonElement constructor
=========================

::: {.section .multi-line-signature}
ButtonElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ButtonElement() => JS<ButtonElement>(
    'returns:ButtonElement;creates:ButtonElement;new:true',
    '#.createElement(#)',
    document,
    "button");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ButtonElement/ButtonElement.html>
:::
