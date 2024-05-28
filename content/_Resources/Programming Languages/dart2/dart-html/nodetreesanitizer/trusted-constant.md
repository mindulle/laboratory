[dart:html](../../dart-html/dart-html-library){._links-link}

trusted constant
================

::: {.section .multi-line-signature}
\_TrustedHtmlTreeSanitizer const trusted
:::

A sanitizer for trees that we trust. It does no validation and allows
any elements. It is also more efficient, since it can pass the text
directly through to the underlying APIs without creating a document
fragment to be sanitized.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const trusted = const _TrustedHtmlTreeSanitizer();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeTreeSanitizer/trusted-constant.html>
:::
