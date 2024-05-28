[dart:html](../../dart-html/dart-html-library){._links-link}

supportsImport property
=======================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsImport
:::

Checks if HTML imports are supported on the current platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get supportsImport {
  return JS('bool', '("import" in #)', this);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/LinkElement/supportsImport.html>
:::
