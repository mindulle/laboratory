[dart:math](../../dart-math/dart-math-library){._links-link}

bottomLeft property
===================

::: {#getter .section .multi-line-signature}
[Point](../point-class)\<T\> bottomLeft

::: {.features}
inherited
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Point<T> get bottomLeft => Point<T>(this.left, (this.top + this.height) as T);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Rectangle/bottomLeft.html>
:::
