[dart:core](../../dart-core/dart-core-library){._links-link}

isUtc property
==============

::: {.section .multi-line-signature}
[bool](../bool-class) isUtc

::: {.features}
final
:::
:::

True if this [DateTime](../datetime-class) is set to UTC time.

``` {.language-dart data-language="dart"}
final dDay = DateTime.utc(1944, 6, 6);
print(dDay.isUtc); // true

final local = DateTime(1944, 6, 6);
print(local.isUtc); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final bool isUtc;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/isUtc.html>
:::
