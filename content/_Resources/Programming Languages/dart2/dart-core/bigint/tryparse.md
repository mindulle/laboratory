[dart:core](../../dart-core/dart-core-library){._links-link}

tryParse method
===============

::: {.section .multi-line-signature}
[BigInt](../bigint-class)? tryParse(

1.  [String](../string-class) source,
2.  {[int](../int-class)? radix}

)
:::

Parses `source` as a, possibly signed, integer literal and returns its
value.

As [parse](parse) except that this method returns `null` if the input is
not valid

Examples:

``` {.language-dart data-language="dart"}
print(BigInt.tryParse('-12345678901234567890')); // -12345678901234567890
print(BigInt.tryParse('0xFF')); // 255
print(BigInt.tryParse('0xffffffffffffffff')); // 18446744073709551615

// From binary (base 2) value.
print(BigInt.tryParse('1100', radix: 2)); // 12
print(BigInt.tryParse('00011111', radix: 2)); // 31
print(BigInt.tryParse('011111100101', radix: 2)); // 2021
// From octal (base 8) value.
print(BigInt.tryParse('14', radix: 8)); // 12
print(BigInt.tryParse('37', radix: 8)); // 31
print(BigInt.tryParse('3745', radix: 8)); // 2021
// From hexadecimal (base 16) value.
print(BigInt.tryParse('c', radix: 16)); // 12
print(BigInt.tryParse('1f', radix: 16)); // 31
print(BigInt.tryParse('7e5', radix: 16)); // 2021
// From base 35 value.
print(BigInt.tryParse('y1', radix: 35)); // 1191 == 34 * 35 + 1
print(BigInt.tryParse('z1', radix: 35)); // null
// From base 36 value.
print(BigInt.tryParse('y1', radix: 36)); // 1225 == 34 * 36 + 1
print(BigInt.tryParse('z1', radix: 36)); // 1261 == 35 * 36 + 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static BigInt? tryParse(String source, {int? radix});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/tryParse.html>
:::
