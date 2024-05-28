[dart:core](../../dart-core/dart-core-library){._links-link}

operator \* method
==================

::: {.section .multi-line-signature}
[String](../string-class) operator \*(

1.  [int](../int-class) times

)
:::

Creates a new string by concatenating this string with itself a number
of times.

The result of `str * n` is equivalent to `str + str + ...`(n
times)`... + str`.

``` {.language-dart data-language="dart"}
const string = 'Dart';
final multiplied = string * 3;
print(multiplied); // 'DartDartDart'
```

Returns an empty string if `times` is zero or negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String operator *(int times);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/operator_multiply.html>
:::
