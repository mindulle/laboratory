[dart:html](../../dart-html/dart-html-library){._links-link}

UListElement constructor
========================

::: {.section .multi-line-signature}
UListElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory UListElement() => JS<UListElement>(
    'returns:UListElement;creates:UListElement;new:true',
    '#.createElement(#)',
    document,
    "ul");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/UListElement/UListElement.html>
:::
