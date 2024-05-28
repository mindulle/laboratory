[dart:core](../../dart-core/dart-core-library){._links-link}

tryParse method
===============

::: {.section .multi-line-signature}
[int](../int-class)? tryParse(

1.  [String](../string-class) source,
2.  {[int](../int-class)? radix}

)

::: {.features}
override
:::
:::

Parse `source` as a, possibly signed, integer literal.

Like [parse](parse) except that this function returns `null` where a
similar call to [parse](parse) would throw a
[FormatException](../formatexception-class).

Example:

``` {.language-dart data-language="dart"}
print(int.tryParse('2021')); // 2021
print(int.tryParse('1f')); // null
// From binary (base 2) value.
print(int.tryParse('1100', radix: 2)); // 12
print(int.tryParse('00011111', radix: 2)); // 31
print(int.tryParse('011111100101', radix: 2)); // 2021
// From octal (base 8) value.
print(int.tryParse('14', radix: 8)); // 12
print(int.tryParse('37', radix: 8)); // 31
print(int.tryParse('3745', radix: 8)); // 2021
// From hexadecimal (base 16) value.
print(int.tryParse('c', radix: 16)); // 12
print(int.tryParse('1f', radix: 16)); // 31
print(int.tryParse('7e5', radix: 16)); // 2021
// From base 35 value.
print(int.tryParse('y1', radix: 35)); // 1191 == 34 * 35 + 1
print(int.tryParse('z1', radix: 35)); // null
// From base 36 value.
print(int.tryParse('y1', radix: 36)); // 1225 == 34 * 36 + 1
print(int.tryParse('z1', radix: 36)); // 1261 == 35 * 36 + 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static int? tryParse(String source, {int? radix});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/tryParse.html>
:::
