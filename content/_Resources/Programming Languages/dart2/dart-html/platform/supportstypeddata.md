[dart:html](../../dart-html/dart-html-library){._links-link}

supportsTypedData property
==========================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsTypedData

::: {.features}
final
:::
:::

Returns true if dart:typed\_data types are supported on this browser. If
false, using these types will generate a runtime error.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static final bool supportsTypedData = JS('bool', '!!(window.ArrayBuffer)');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Platform/supportsTypedData.html>
:::
