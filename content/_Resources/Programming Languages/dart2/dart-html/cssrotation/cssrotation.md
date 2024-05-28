[dart:html](../../dart-html/dart-html-library){._links-link}

CssRotation constructor
=======================

::: {.section .multi-line-signature}
CssRotation(

1.  dynamic angleValue\_OR\_x,
2.  \[[num](../../dart-core/num-class)? y,
3.  [num](../../dart-core/num-class)? z,
4.  [CssNumericValue](../cssnumericvalue-class)? angle\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CssRotation(angleValue_OR_x,
    [num? y, num? z, CssNumericValue? angle]) {
  if ((angleValue_OR_x is CssNumericValue) &&
      y == null &&
      z == null &&
      angle == null) {
    return CssRotation._create_1(angleValue_OR_x);
  }
  if ((angle is CssNumericValue) &&
      (z is num) &&
      (y is num) &&
      (angleValue_OR_x is num)) {
    return CssRotation._create_2(angleValue_OR_x, y, z, angle);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRotation/CssRotation.html>
:::
