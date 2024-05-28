[dart:html](../../dart-html/dart-html-library){._links-link}

LinkElement constructor
=======================

::: {.section .multi-line-signature}
LinkElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory LinkElement() => JS<LinkElement>(
    'returns:LinkElement;creates:LinkElement;new:true',
    '#.createElement(#)',
    document,
    "link");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/LinkElement/LinkElement.html>
:::
