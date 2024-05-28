[dart:core](../../dart-core/dart-core-library){._links-link}

inHours property
================

::: {#getter .section .multi-line-signature}
[int](../int-class) inHours
:::

The number of entire hours spanned by this
[Duration](../duration-class).

The returned value can be greater than 23. For example, a duration of
four days and three hours has 99 entire hours.

``` {.language-dart data-language="dart"}
const duration = Duration(days: 4, hours: 3);
print(duration.inHours); // 99
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get inHours => _duration ~/ Duration.microsecondsPerHour;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/inHours.html>
:::
