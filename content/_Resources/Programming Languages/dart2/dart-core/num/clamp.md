[dart:core](../../dart-core/dart-core-library){._links-link}

clamp method
============

::: {.section .multi-line-signature}
[num](../num-class) clamp(

1.  [num](../num-class) lowerLimit,
2.  [num](../num-class) upperLimit

)
:::

Returns this [num](../num-class) clamped to be in the range
`lowerLimit`-`upperLimit`.

The comparison is done using [compareTo](compareto) and therefore takes
`-0.0` into account. This also implies that
[double.nan](../double/nan-constant) is treated as the maximal double
value.

The arguments `lowerLimit` and `upperLimit` must form a valid range
where `lowerLimit.compareTo(upperLimit) <= 0`.

Example:

``` {.language-dart data-language="dart"}
var result = 10.5.clamp(5, 10.0); // 10.0
result = 0.75.clamp(5, 10.0); // 5
result = (-10).clamp(-5, 5.0); // -5
result = (-0.0).clamp(-5, 5.0); // -0.0
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
num clamp(num lowerLimit, num upperLimit);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/clamp.html>
:::
