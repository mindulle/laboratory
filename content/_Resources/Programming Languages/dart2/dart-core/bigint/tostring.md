[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Returns a String-representation of this integer.

The returned string is parsable by [parse](parse). For any `BigInt` `i`,
it is guaranteed that `i == BigInt.parse(i.toString())`.

Example:

``` {.language-dart data-language="dart"}
var bigNumber = BigInt.parse('100000000000000000000000');
print(bigNumber.toString()); // "100000000000000000000000"
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/toString.html>
:::
