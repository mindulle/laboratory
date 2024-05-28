[dart:core](../../dart-core/dart-core-library){._links-link}

tryParse method
===============

::: {.section .multi-line-signature}
[double](../double-class)? tryParse(

1.  [String](../string-class) source

)

::: {.features}
override
:::
:::

Parse `source` as a double literal and return its value.

Like [parse](parse), except that this function returns `null` for
invalid inputs instead of throwing.

Example:

``` {.language-dart data-language="dart"}
var value = double.tryParse('3.14'); // 3.14
value = double.tryParse('  3.14 \xA0'); // 3.14
value = double.tryParse('0.'); // 0.0
value = double.tryParse('.0'); // 0.0
value = double.tryParse('-1.e3'); // -1000.0
value = double.tryParse('1234E+7'); // 12340000000.0
value = double.tryParse('+.12e-9'); // 1.2e-10
value = double.tryParse('-NaN'); // NaN
value = double.tryParse('0xFF'); // null
value = double.tryParse(double.infinity.toString()); // Infinity
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static double? tryParse(String source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/tryParse.html>
:::
