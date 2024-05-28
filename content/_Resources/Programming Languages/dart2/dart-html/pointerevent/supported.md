[dart:html](../../dart-html/dart-html-library){._links-link}

supported property
==================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supported
:::

PointerEvent used for both touch and mouse. To check if touch is
supported call the property TouchEvent.supported

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supported {
  try {
    return PointerEvent('pointerover') is PointerEvent;
  } catch (_) {}
  return false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PointerEvent/supported.html>
:::
