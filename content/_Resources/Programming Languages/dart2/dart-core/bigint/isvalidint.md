[dart:core](../../dart-core/dart-core-library){._links-link}

isValidInt property
===================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isValidInt
:::

Whether this big integer can be represented as an `int` without losing
precision.

**Warning:** this function may give a different result on dart2js, dev
compiler, and the VM, due to the differences in integer precision.

Example:

``` {.language-dart data-language="dart"}
var bigNumber = BigInt.parse('100000000000000000000000');
print(bigNumber.isValidInt); // false

var value = BigInt.parse('0xFF'); // 255
print(value.isValidInt); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isValidInt;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/isValidInt.html>
:::
