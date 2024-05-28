[dart:core](../../dart-core/dart-core-library){._links-link}

BigInt.from constructor
=======================

::: {.section .multi-line-signature}
BigInt.from(

1.  [num](../num-class) value

)
:::

Creates a big integer from the provided `value` number.

Examples:

``` {.language-dart data-language="dart"}
var bigInteger = BigInt.from(1); // 1
bigInteger = BigInt.from(0.9999); // 0
bigInteger = BigInt.from(-10.99); // -10
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory BigInt.from(num value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/BigInt.from.html>
:::
