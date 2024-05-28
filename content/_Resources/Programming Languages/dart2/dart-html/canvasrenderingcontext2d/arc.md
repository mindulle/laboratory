[dart:html](../../dart-html/dart-html-library){._links-link}

arc method
==========

::: {.section .multi-line-signature}
void arc(

1.  [num](../../dart-core/num-class) x,
2.  [num](../../dart-core/num-class) y,
3.  [num](../../dart-core/num-class) radius,
4.  [num](../../dart-core/num-class) startAngle,
5.  [num](../../dart-core/num-class) endAngle,
6.  \[[bool](../../dart-core/bool-class) anticlockwise = false\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void arc(num x, num y, num radius, num startAngle, num endAngle,
    [bool anticlockwise = false]) {
  // TODO(terry): This should not be needed: dartbug.com/20939.
  JS('void', '#.arc(#, #, #, #, #, #)', this, x, y, radius, startAngle,
      endAngle, anticlockwise);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/arc.html>
:::
