[dart:html](../../dart-html/dart-html-library){._links-link}

supported property
==================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supported
:::

Returns true if this input type is supported on the current platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supported {
  return (new InputElement(type: 'email')).type == 'email';
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/EmailInputElement/supported.html>
:::
