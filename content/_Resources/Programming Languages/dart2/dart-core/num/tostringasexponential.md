[dart:core](../../dart-core/dart-core-library){._links-link}

toStringAsExponential method
============================

::: {.section .multi-line-signature}
[String](../string-class) toStringAsExponential(

1.  \[[int](../int-class)? fractionDigits\]

)
:::

An exponential string-representation of this number.

Converts this number to a [double](../double-class) before computing the
string representation.

If `fractionDigits` is given, then it must be an integer satisfying:
`0 <= fractionDigits <= 20`. In this case the string contains exactly
`fractionDigits` after the decimal point. Otherwise, without the
parameter, the returned string uses the shortest number of digits that
accurately represent this number.

If `fractionDigits` equals 0, then the decimal point is omitted.
Examples:

``` {.language-dart data-language="dart"}
1.toStringAsExponential();       // 1e+0
1.toStringAsExponential(3);      // 1.000e+0
123456.toStringAsExponential();  // 1.23456e+5
123456.toStringAsExponential(3); // 1.235e+5
123.toStringAsExponential(0);    // 1e+2
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toStringAsExponential([int? fractionDigits]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/toStringAsExponential.html>
:::
