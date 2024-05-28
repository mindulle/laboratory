[dart:html](../../dart-html/dart-html-library){._links-link}

Range.fromPoint constructor
===========================

::: {.section .multi-line-signature}
Range.fromPoint(

1.  [Point](../../dart-math/point-class)\<[num](../../dart-core/num-class)\>
    point

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Range.fromPoint(Point point) =>
    document._caretRangeFromPoint(point.x.toInt(), point.y.toInt());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Range/Range.fromPoint.html>
:::
