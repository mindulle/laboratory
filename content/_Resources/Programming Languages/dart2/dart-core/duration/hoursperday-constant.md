[dart:core](../../dart-core/dart-core-library){._links-link}

hoursPerDay constant
====================

::: {.section .multi-line-signature}
[int](../int-class) const hoursPerDay
:::

The number of hours per day.

Notice that some days may differ in length because of time zone changes
due to daylight saving. The [Duration](../duration-class) class is time
zone agnostic and considers all days to have 24 hours.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const int hoursPerDay = 24;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/hoursPerDay-constant.html>
:::
