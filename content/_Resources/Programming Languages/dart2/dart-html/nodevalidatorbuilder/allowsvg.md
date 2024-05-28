[dart:html](../../dart-html/dart-html-library){._links-link}

allowSvg method
===============

::: {.section .multi-line-signature}
void allowSvg()
:::

Allow SVG elements and attributes except for known bad ones.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowSvg() {
  add(new _SvgNodeValidator());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowSvg.html>
:::
