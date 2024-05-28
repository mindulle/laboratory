[dart:core](../../dart-core/dart-core-library){._links-link}

toStringAsFixed method
======================

::: {.section .multi-line-signature}
[String](../string-class) toStringAsFixed(

1.  [int](../int-class) fractionDigits

)
:::

A decimal-point string-representation of this number.

Converts this number to a [double](../double-class) before computing the
string representation, as by [toDouble](todouble).

If the absolute value of `this` is greater than or equal to `10^21`,
then this methods returns an exponential representation computed by
`this.toStringAsExponential()`. Otherwise the result is the closest
string representation with exactly `fractionDigits` digits after the
decimal point. If `fractionDigits` equals 0, then the decimal point is
omitted.

The parameter `fractionDigits` must be an integer satisfying:
`0 <= fractionDigits <= 20`.

Examples:

``` {.language-dart data-language="dart"}
1.toStringAsFixed(3);  // 1.000
(4321.12345678).toStringAsFixed(3);  // 4321.123
(4321.12345678).toStringAsFixed(5);  // 4321.12346
123456789012345.toStringAsFixed(3);  // 123456789012345.000
10000000000000000.toStringAsFixed(4); // 10000000000000000.0000
5.25.toStringAsFixed(0); // 5
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toStringAsFixed(int fractionDigits);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/toStringAsFixed.html>
:::
