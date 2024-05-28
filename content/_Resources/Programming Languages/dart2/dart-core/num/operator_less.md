[dart:core](../../dart-core/dart-core-library){._links-link}

operator \< method
==================

::: {.section .multi-line-signature}
[bool](../bool-class) operator \<(

1.  [num](../num-class) other

)
:::

Whether this number is numerically smaller than `other`.

Returns `true` if this number is smaller than `other`. Returns `false`
if this number is greater than or equal to `other` or if either value is
a NaN value like [double.nan](../double/nan-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator <(num other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/operator_less.html>
:::
