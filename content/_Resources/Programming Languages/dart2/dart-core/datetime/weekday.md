[dart:core](../../dart-core/dart-core-library){._links-link}

weekday property
================

::: {#getter .section .multi-line-signature}
[int](../int-class) weekday
:::

The day of the week
[monday](monday-constant)..[sunday](sunday-constant).

In accordance with ISO 8601 a week starts with Monday, which has the
value 1.

``` {.language-dart data-language="dart"}
final moonLanding = DateTime.parse('1969-07-20 20:18:04Z');
print(moonLanding.weekday); // 7
assert(moonLanding.weekday == DateTime.sunday);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int get weekday;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/weekday.html>
:::
