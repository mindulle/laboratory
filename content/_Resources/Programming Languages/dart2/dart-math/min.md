[dart:math](../dart-math/dart-math-library){._links-link}

min\<T extends num\> function
=============================

::: {.section .multi-line-signature}
T min\<T extends num\>(

1.  T a,
2.  T b

)
:::

Returns the lesser of two numbers.

Returns NaN if either argument is NaN. The lesser of `-0.0` and `0.0` is
`-0.0`. If the arguments are otherwise equal (including int and doubles
with the same mathematical value) then it is unspecified which of the
two arguments is returned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external T min<T extends num>(T a, T b);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/min.html>
:::
