[dart:math](../../dart-math/dart-math-library){._links-link}

Point\<T extends num\> constructor
==================================

::: {.section .multi-line-signature}
const Point\<T extends num\>(

1.  T x,
2.  T y

)
:::

Creates a point with the provided `x` and `y` coordinates.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Point(T x, T y)
    : this.x = x,
      this.y = y;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/Point.html>
:::
