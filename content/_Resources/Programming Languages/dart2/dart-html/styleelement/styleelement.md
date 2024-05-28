[dart:html](../../dart-html/dart-html-library){._links-link}

StyleElement constructor
========================

::: {.section .multi-line-signature}
StyleElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StyleElement() => JS<StyleElement>(
    'returns:StyleElement;creates:StyleElement;new:true',
    '#.createElement(#)',
    document,
    "style");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/StyleElement/StyleElement.html>
:::
