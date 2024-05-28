[dart:html](../../dart-html/dart-html-library){._links-link}

DomRectReadOnly constructor
===========================

::: {.section .multi-line-signature}
DomRectReadOnly(

1.  \[[num](../../dart-core/num-class)? x,
2.  [num](../../dart-core/num-class)? y,
3.  [num](../../dart-core/num-class)? width,
4.  [num](../../dart-core/num-class)? height\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DomRectReadOnly([num? x, num? y, num? width, num? height]) {
  if (height != null) {
    return DomRectReadOnly._create_1(x, y, width, height);
  }
  if (width != null) {
    return DomRectReadOnly._create_2(x, y, width);
  }
  if (y != null) {
    return DomRectReadOnly._create_3(x, y);
  }
  if (x != null) {
    return DomRectReadOnly._create_4(x);
  }
  return DomRectReadOnly._create_5();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomRectReadOnly/DomRectReadOnly.html>
:::
