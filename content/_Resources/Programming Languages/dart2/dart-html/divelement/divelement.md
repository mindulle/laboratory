[dart:html](../../dart-html/dart-html-library){._links-link}

DivElement constructor
======================

::: {.section .multi-line-signature}
DivElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DivElement() => JS<DivElement>(
    'returns:DivElement;creates:DivElement;new:true',
    '#.createElement(#)',
    document,
    "div");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DivElement/DivElement.html>
:::
