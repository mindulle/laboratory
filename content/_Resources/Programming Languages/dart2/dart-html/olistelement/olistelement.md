[dart:html](../../dart-html/dart-html-library){._links-link}

OListElement constructor
========================

::: {.section .multi-line-signature}
OListElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory OListElement() => JS<OListElement>(
    'returns:OListElement;creates:OListElement;new:true',
    '#.createElement(#)',
    document,
    "ol");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/OListElement/OListElement.html>
:::
