[dart:core](../../dart-core/dart-core-library){._links-link}

inDays property
===============

::: {#getter .section .multi-line-signature}
[int](../int-class) inDays
:::

The number of entire days spanned by this [Duration](../duration-class).

For example, a duration of four days and three hours has four entire
days.

``` {.language-dart data-language="dart"}
const duration = Duration(days: 4, hours: 3);
print(duration.inDays); // 4
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get inDays => _duration ~/ Duration.microsecondsPerDay;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/inDays.html>
:::
