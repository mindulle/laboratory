[dart:math](../dart-math/dart-math-library){._links-link}

log function
============

::: {.section .multi-line-signature}
[double](../dart-core/double-class) log(

1.  [num](../dart-core/num-class) x

)
:::

Converts `x` to a [double](../dart-core/double-class) and returns the
natural logarithm of the value.

Returns negative infinity if `x` is equal to zero. Returns NaN if `x` is
NaN or less than zero.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external double log(num x);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/log.html>
:::
