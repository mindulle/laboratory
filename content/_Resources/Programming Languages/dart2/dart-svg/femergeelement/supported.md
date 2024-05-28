[dart:svg](../../dart-svg/dart-svg-library){._links-link}

supported property
==================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supported
:::

Checks if this type is supported on the current platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supported =>
    SvgElement.isTagSupported('feMerge') &&
    (new SvgElement.tag('feMerge') is FEMergeElement);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/FEMergeElement/supported.html>
:::
