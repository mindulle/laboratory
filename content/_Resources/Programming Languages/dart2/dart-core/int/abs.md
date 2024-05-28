[dart:core](../../dart-core/dart-core-library){._links-link}

abs method
==========

::: {.section .multi-line-signature}
[int](../int-class) abs()

::: {.features}
override
:::
:::

Returns the absolute value of this integer.

For any integer `value`, the result is the same as
`value < 0 ? -value : value`.

Integer overflow may cause the result of `-value` to stay negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int abs();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/abs.html>
:::
