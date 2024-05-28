[dart:html](../../dart-html/dart-html-library){._links-link}

BaseElement constructor
=======================

::: {.section .multi-line-signature}
BaseElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory BaseElement() => JS<BaseElement>(
    'returns:BaseElement;creates:BaseElement;new:true',
    '#.createElement(#)',
    document,
    "base");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BaseElement/BaseElement.html>
:::
