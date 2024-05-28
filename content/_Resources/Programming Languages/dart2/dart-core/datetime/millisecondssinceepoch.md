[dart:core](../../dart-core/dart-core-library){._links-link}

millisecondsSinceEpoch property
===============================

::: {#getter .section .multi-line-signature}
[int](../int-class) millisecondsSinceEpoch
:::

The number of milliseconds since the \"Unix epoch\" 1970-01-01T00:00:00Z
(UTC).

This value is independent of the time zone.

This value is at most 8,640,000,000,000,000ms (100,000,000 days) from
the Unix epoch. In other words:
`millisecondsSinceEpoch.abs() <= 8640000000000000`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int get millisecondsSinceEpoch;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/millisecondsSinceEpoch.html>
:::
