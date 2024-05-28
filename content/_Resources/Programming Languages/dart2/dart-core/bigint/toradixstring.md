[dart:core](../../dart-core/dart-core-library){._links-link}

toRadixString method
====================

::: {.section .multi-line-signature}
[String](../string-class) toRadixString(

1.  [int](../int-class) radix

)
:::

Converts [this](../bigint-class) to a string representation in the given
`radix`.

In the string representation, lower-case letters are used for digits
above \'9\', with \'a\' being 10 an \'z\' being 35.

The `radix` argument must be an integer in the range 2 to 36.

Example:

``` {.language-dart data-language="dart"}
// Binary (base 2).
print(BigInt.from(12).toRadixString(2)); // 1100
print(BigInt.from(31).toRadixString(2)); // 11111
print(BigInt.from(2021).toRadixString(2)); // 11111100101
print(BigInt.from(-12).toRadixString(2)); // -1100
// Octal (base 8).
print(BigInt.from(12).toRadixString(8)); // 14
print(BigInt.from(31).toRadixString(8)); // 37
print(BigInt.from(2021).toRadixString(8)); // 3745
// Hexadecimal (base 16).
print(BigInt.from(12).toRadixString(16)); // c
print(BigInt.from(31).toRadixString(16)); // 1f
print(BigInt.from(2021).toRadixString(16)); // 7e5
// Base 36.
print(BigInt.from(35 * 36 + 1).toRadixString(36)); // z1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toRadixString(int radix);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/toRadixString.html>
:::
