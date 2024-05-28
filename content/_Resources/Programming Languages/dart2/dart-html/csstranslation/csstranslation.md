[dart:html](../../dart-html/dart-html-library){._links-link}

CssTranslation constructor
==========================

::: {.section .multi-line-signature}
CssTranslation(

1.  [CssNumericValue](../cssnumericvalue-class) x,
2.  [CssNumericValue](../cssnumericvalue-class) y,
3.  \[[CssNumericValue](../cssnumericvalue-class)? z\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CssTranslation(CssNumericValue x, CssNumericValue y,
    [CssNumericValue? z]) {
  if ((y is CssNumericValue) && (x is CssNumericValue) && z == null) {
    return CssTranslation._create_1(x, y);
  }
  if ((z is CssNumericValue) &&
      (y is CssNumericValue) &&
      (x is CssNumericValue)) {
    return CssTranslation._create_2(x, y, z);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssTranslation/CssTranslation.html>
:::
