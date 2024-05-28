[dart:core](../../dart-core/dart-core-library){._links-link}

abs method
==========

::: {.section .multi-line-signature}
[num](../num-class) abs()
:::

The absolute value of this number.

The absolute value is the value itself, if the value is non-negative,
and `-value` if the value is negative.

Integer overflow may cause the result of `-value` to stay negative.

``` {.language-dart data-language="dart"}
print((2).abs()); // 2
print((-2.5).abs()); // 2.5
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num abs();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/abs.html>
:::
