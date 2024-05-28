[dart:html](../../dart-html/dart-html-library){._links-link}

QuoteElement constructor
========================

::: {.section .multi-line-signature}
QuoteElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory QuoteElement() => JS<QuoteElement>(
    'returns:QuoteElement;creates:QuoteElement;new:true',
    '#.createElement(#)',
    document,
    "q");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/QuoteElement/QuoteElement.html>
:::
