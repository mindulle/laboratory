[dart:html](../../dart-html/dart-html-library){._links-link}

CssScale constructor
====================

::: {.section .multi-line-signature}
CssScale(

1.  [num](../../dart-core/num-class) x,
2.  [num](../../dart-core/num-class) y,
3.  \[[num](../../dart-core/num-class)? z\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CssScale(num x, num y, [num? z]) {
  if ((y is num) && (x is num) && z == null) {
    return CssScale._create_1(x, y);
  }
  if ((z is num) && (y is num) && (x is num)) {
    return CssScale._create_2(x, y, z);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssScale/CssScale.html>
:::
