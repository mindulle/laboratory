[dart:math](../dart-math/dart-math-library){._links-link}

sqrt function
=============

::: {.section .multi-line-signature}
[double](../dart-core/double-class) sqrt(

1.  [num](../dart-core/num-class) x

)
:::

Converts `x` to a [double](../dart-core/double-class) and returns the
positive square root of the value.

Returns -0.0 if `x` is -0.0, and NaN if `x` is otherwise negative or
NaN.

``` {.language-dart data-language="dart"}
var result = sqrt(9.3);
print(result); // 3.0495901363953815
result = sqrt(2);
print(result); // 1.4142135623730951
result = sqrt(0);
print(result); // 0.0
result = sqrt(-2.2);
print(result); // NaN
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external double sqrt(num x);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/sqrt.html>
:::
