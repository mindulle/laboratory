[dart:html](../../dart-html/dart-html-library){._links-link}

CssStyleDeclaration.css constructor
===================================

::: {.section .multi-line-signature}
CssStyleDeclaration.css(

1.  [String](../../dart-core/string-class) css

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CssStyleDeclaration.css(String css) {
  final style = new DivElement().style;
  style.cssText = css;
  return style;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/CssStyleDeclaration.css.html>
:::
