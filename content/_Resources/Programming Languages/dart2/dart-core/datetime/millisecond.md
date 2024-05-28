[dart:core](../../dart-core/dart-core-library){._links-link}

millisecond property
====================

::: {#getter .section .multi-line-signature}
[int](../int-class) millisecond
:::

The millisecond `[0...999]`.

``` {.language-dart data-language="dart"}
final date = DateTime.parse('1970-01-01 05:01:01.234567Z');
print(date.millisecond); // 234
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int get millisecond;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/millisecond.html>
:::
