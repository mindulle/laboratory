[dart:html](../../dart-html/dart-html-library){._links-link}

SelectElement constructor
=========================

::: {.section .multi-line-signature}
SelectElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SelectElement() => JS<SelectElement>(
    'returns:SelectElement;creates:SelectElement;new:true',
    '#.createElement(#)',
    document,
    "select");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SelectElement/SelectElement.html>
:::
