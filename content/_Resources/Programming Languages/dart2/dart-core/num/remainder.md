[dart:core](../../dart-core/dart-core-library){._links-link}

remainder method
================

::: {.section .multi-line-signature}
[num](../num-class) remainder(

1.  [num](../num-class) other

)
:::

The remainder of the truncating division of `this` by `other`.

The result `r` of this operation satisfies:
`this == (this ~/ other) * other + r`. As a consequence, the remainder
`r` has the same sign as the divider `this`.

The result is an [int](../int-class), as described by
[int.remainder](remainder), if both this number and `other` are
integers, otherwise the result is a [double](../double-class).

Example:

``` {.language-dart data-language="dart"}
print(5.remainder(3)); // 2
print(-5.remainder(3)); // -2
print(5.remainder(-3)); // 2
print(-5.remainder(-3)); // -2
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num remainder(num other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/remainder.html>
:::
