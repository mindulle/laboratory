[dart:core](../../dart-core/dart-core-library){._links-link}

truncate method
===============

::: {.section .multi-line-signature}
[int](../int-class) truncate()

::: {.features}
override
:::
:::

Returns the integer obtained by discarding any fractional part of this
number.

Rounds the number towards zero.

Throws an [UnsupportedError](../unsupportederror-class) if this number
is not finite (NaN or an infinity).

``` {.language-dart data-language="dart"}
print(2.00001.truncate()); // 2
print(1.99999.truncate()); // 1
print(0.5.truncate()); // 0
print((-0.5).truncate()); // 0
print((-1.5).truncate()); // -1
print((-2.5).truncate()); // -2
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int truncate();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/truncate.html>
:::
