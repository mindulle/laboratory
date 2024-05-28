[dart:core](../../dart-core/dart-core-library){._links-link}

pow method
==========

::: {.section .multi-line-signature}
[BigInt](../bigint-class) pow(

1.  [int](../int-class) exponent

)
:::

Returns `this` to the power of `exponent`.

Returns [one](one) if the `exponent` equals 0.

The `exponent` must otherwise be positive.

The result is always equal to the mathematical result of this to the
power `exponent`, only limited by the available memory.

Example:

``` {.language-dart data-language="dart"}
var value = BigInt.from(1000);
print(value.pow(0)); // 1
print(value.pow(1)); // 1000
print(value.pow(2)); // 1000000
print(value.pow(3)); // 1000000000
print(value.pow(4)); // 1000000000000
print(value.pow(5)); // 1000000000000000
print(value.pow(6)); // 1000000000000000000
print(value.pow(7)); // 1000000000000000000000
print(value.pow(8)); // 1000000000000000000000000
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt pow(int exponent);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/pow.html>
:::
