[dart:core](../../dart-core/dart-core-library){._links-link}

toStringAsPrecision method
==========================

::: {.section .multi-line-signature}
[String](../string-class) toStringAsPrecision(

1.  [int](../int-class) precision

)
:::

A string representation with `precision` significant digits.

Converts this number to a [double](../double-class) and returns a string
representation of that value with exactly `precision` significant
digits.

The parameter `precision` must be an integer satisfying:
`1 <= precision <= 21`.

Examples:

``` {.language-dart data-language="dart"}
1.toStringAsPrecision(2);       // 1.0
1e15.toStringAsPrecision(3);    // 1.00e+15
1234567.toStringAsPrecision(3); // 1.23e+6
1234567.toStringAsPrecision(9); // 1234567.00
12345678901234567890.toStringAsPrecision(20); // 12345678901234567168
12345678901234567890.toStringAsPrecision(14); // 1.2345678901235e+19
0.00000012345.toStringAsPrecision(15); // 1.23450000000000e-7
0.0000012345.toStringAsPrecision(15);  // 0.00000123450000000000
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toStringAsPrecision(int precision);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/toStringAsPrecision.html>
:::
