[dart:html](../../dart-html/dart-html-library){._links-link}

DomQuad constructor
===================

::: {.section .multi-line-signature}
DomQuad(

1.  \[[Map](../../dart-core/map-class)? p1,
2.  [Map](../../dart-core/map-class)? p2,
3.  [Map](../../dart-core/map-class)? p3,
4.  [Map](../../dart-core/map-class)? p4\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DomQuad([Map? p1, Map? p2, Map? p3, Map? p4]) {
  if (p4 != null) {
    var p1_1 = convertDartToNative_Dictionary(p1);
    var p2_2 = convertDartToNative_Dictionary(p2);
    var p3_3 = convertDartToNative_Dictionary(p3);
    var p4_4 = convertDartToNative_Dictionary(p4);
    return DomQuad._create_1(p1_1, p2_2, p3_3, p4_4);
  }
  if (p3 != null) {
    var p1_1 = convertDartToNative_Dictionary(p1);
    var p2_2 = convertDartToNative_Dictionary(p2);
    var p3_3 = convertDartToNative_Dictionary(p3);
    return DomQuad._create_2(p1_1, p2_2, p3_3);
  }
  if (p2 != null) {
    var p1_1 = convertDartToNative_Dictionary(p1);
    var p2_2 = convertDartToNative_Dictionary(p2);
    return DomQuad._create_3(p1_1, p2_2);
  }
  if (p1 != null) {
    var p1_1 = convertDartToNative_Dictionary(p1);
    return DomQuad._create_4(p1_1);
  }
  return DomQuad._create_5();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomQuad/DomQuad.html>
:::
