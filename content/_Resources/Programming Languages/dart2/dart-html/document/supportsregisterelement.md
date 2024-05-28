[dart:html](../../dart-html/dart-html-library){._links-link}

supportsRegisterElement property
================================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsRegisterElement
:::

Checks if [registerElement](registerelement) is supported on the current
platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get supportsRegisterElement {
  return JS('bool', '("registerElement" in #)', this);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/supportsRegisterElement.html>
:::
