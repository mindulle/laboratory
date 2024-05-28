[dart:core](../../dart-core/dart-core-library){._links-link}

ceil method
===========

::: {.section .multi-line-signature}
[int](../int-class) ceil()

::: {.features}
override
:::
:::

Returns the least integer that is not smaller than this number.

Rounds the number towards infinity.

Throws an [UnsupportedError](../unsupportederror-class) if this number
is not finite (NaN or an infinity).

``` {.language-dart data-language="dart"}
print(1.99999.ceil()); // 2
print(2.0.ceil()); // 2
print(2.00001.ceil()); // 3
print((-1.99999).ceil()); // -1
print((-2.0).ceil()); // -2
print((-2.00001).ceil()); // -2
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int ceil();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/ceil.html>
:::
