[dart:html](../../dart-html/dart-html-library){._links-link}

LIElement constructor
=====================

::: {.section .multi-line-signature}
LIElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory LIElement() => JS<LIElement>(
    'returns:LIElement;creates:LIElement;new:true',
    '#.createElement(#)',
    document,
    "li");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/LIElement/LIElement.html>
:::
