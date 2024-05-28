[dart:html](../../dart-html/dart-html-library){._links-link}

offset property
===============

::: {#getter .section .multi-line-signature}
[Point](../../dart-math/point-class)\<[num](../../dart-core/num-class)\>
offset
:::

The coordinates of the mouse pointer in target node coordinates.

This value may vary between platforms if the target node moves after the
event has fired or if the element has CSS transforms affecting it.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Point get offset {
  if (JS('bool', '!!#.offsetX', this)) {
    var x = JS('int', '#.offsetX', this);
    var y = JS('int', '#.offsetY', this);
    return new Point(x as num, y as num);
  } else {
    // Firefox does not support offsetX.
    if (!(this.target is Element)) {
      throw new UnsupportedError('offsetX is only supported on elements');
    }
    Element target = this.target as Element;
    var point = (this.client - target.getBoundingClientRect().topLeft);
    return new Point(point.x.toInt(), point.y.toInt());
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MouseEvent/offset.html>
:::
