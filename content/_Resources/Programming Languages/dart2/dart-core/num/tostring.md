[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

The shortest string that correctly represents this number.

All [double](../double-class)s in the range `10^-6` (inclusive) to
`10^21` (exclusive) are converted to their decimal representation with
at least one digit after the decimal point. For all other doubles,
except for special values like `NaN` or `Infinity`, this method returns
an exponential representation (see
[toStringAsExponential](tostringasexponential)).

Returns `"NaN"` for [double.nan](../double/nan-constant), `"Infinity"`
for [double.infinity](../double/infinity-constant), and `"-Infinity"`
for [double.negativeInfinity](../double/negativeinfinity-constant).

An [int](../int-class) is converted to a decimal representation with no
decimal point.

Examples:

``` {.language-dart data-language="dart"}
(0.000001).toString();  // "0.000001"
(0.0000001).toString(); // "1e-7"
(111111111111111111111.0).toString();  // "111111111111111110000.0"
(100000000000000000000.0).toString();  // "100000000000000000000.0"
(1000000000000000000000.0).toString(); // "1e+21"
(1111111111111111111111.0).toString(); // "1.1111111111111111e+21"
1.toString(); // "1"
111111111111111111111.toString();  // "111111111111111110000"
100000000000000000000.toString();  // "100000000000000000000"
1000000000000000000000.toString(); // "1000000000000000000000"
1111111111111111111111.toString(); // "1111111111111111111111"
1.234e5.toString();   // 123400
1234.5e6.toString();  // 1234500000
12.345e67.toString(); // 1.2345e+68
```

Note: the conversion may round the output if the returned string is
accurate enough to uniquely identify the input-number. For example the
most precise representation of the [double](../double-class) `9e59`
equals `"899999999999999918767229449717619953810131273674690656206848"`,
but this method returns the shorter (but still uniquely identifying)
`"9e59"`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/toString.html>
:::
