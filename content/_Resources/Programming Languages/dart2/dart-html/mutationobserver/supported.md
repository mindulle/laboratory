[dart:html](../../dart-html/dart-html-library){._links-link}

supported property
==================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supported
:::

Checks to see if the mutation observer API is supported on the current
platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supported {
  return JS(
      'bool', '!!(window.MutationObserver || window.WebKitMutationObserver)');
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MutationObserver/supported.html>
:::
