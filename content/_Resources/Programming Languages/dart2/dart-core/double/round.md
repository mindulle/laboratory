[dart:core](../../dart-core/dart-core-library){._links-link}

round method
============

::: {.section .multi-line-signature}
[int](../int-class) round()

::: {.features}
override
:::
:::

Returns the integer closest to this number.

Rounds away from zero when there is no closest integer:
`(3.5).round() == 4` and `(-3.5).round() == -4`.

Throws an [UnsupportedError](../unsupportederror-class) if this number
is not finite (NaN or an infinity).

``` {.language-dart data-language="dart"}
print(3.0.round()); // 3
print(3.25.round()); // 3
print(3.5.round()); // 4
print(3.75.round()); // 4
print((-3.5).round()); // -4
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int round();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/round.html>
:::
