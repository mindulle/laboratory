[dart:html](../../dart-html/dart-html-library){._links-link}

DomPointReadOnly constructor
============================

::: {.section .multi-line-signature}
DomPointReadOnly(

1.  \[[num](../../dart-core/num-class)? x,
2.  [num](../../dart-core/num-class)? y,
3.  [num](../../dart-core/num-class)? z,
4.  [num](../../dart-core/num-class)? w\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DomPointReadOnly([num? x, num? y, num? z, num? w]) {
  if (w != null) {
    return DomPointReadOnly._create_1(x, y, z, w);
  }
  if (z != null) {
    return DomPointReadOnly._create_2(x, y, z);
  }
  if (y != null) {
    return DomPointReadOnly._create_3(x, y);
  }
  if (x != null) {
    return DomPointReadOnly._create_4(x);
  }
  return DomPointReadOnly._create_5();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomPointReadOnly/DomPointReadOnly.html>
:::
