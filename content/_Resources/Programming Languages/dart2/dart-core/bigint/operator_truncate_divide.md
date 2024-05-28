[dart:core](../../dart-core/dart-core-library){._links-link}

operator \~/ method
===================

::: {.section .multi-line-signature}
[BigInt](../bigint-class) operator \~/(

1.  [BigInt](../bigint-class) other

)
:::

Truncating integer division operator.

Performs a truncating integer division, where the remainder is
discarded.

The remainder can be computed using the [remainder](remainder) method.

Examples:

``` {.language-dart data-language="dart"}
var seven = BigInt.from(7);
var three = BigInt.from(3);
seven ~/ three;    // => 2
(-seven) ~/ three; // => -2
seven ~/ -three;   // => -2
seven.remainder(three);    // => 1
(-seven).remainder(three); // => -1
seven.remainder(-three);   // => 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt operator ~/(BigInt other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/operator_truncate_divide.html>
:::
