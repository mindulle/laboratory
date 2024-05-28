[dart:core](../../dart-core/dart-core-library){._links-link}

tryParse method
===============

::: {.section .multi-line-signature}
[num](../num-class)? tryParse(

1.  [String](../string-class) input

)
:::

Parses a string containing a number literal into a number.

Like [parse](parse), except that this function returns `null` for
invalid inputs instead of throwing.

Examples:

``` {.language-dart data-language="dart"}
var value = num.tryParse('2021'); // 2021
value = num.tryParse('3.14'); // 3.14
value = num.tryParse('  3.14 \xA0'); // 3.14
value = num.tryParse('0.'); // 0.0
value = num.tryParse('.0'); // 0.0
value = num.tryParse('-1.e3'); // -1000.0
value = num.tryParse('1234E+7'); // 12340000000.0
value = num.tryParse('+.12e-9'); // 1.2e-10
value = num.tryParse('-NaN'); // NaN
value = num.tryParse('0xFF'); // 255
value = num.tryParse(double.infinity.toString()); // Infinity
value = num.tryParse('1f'); // null
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static num? tryParse(String input) {
  String source = input.trim();
  // TODO(lrn): Optimize to detect format and result type in one check.
  return int.tryParse(source) ?? double.tryParse(source);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/tryParse.html>
:::
