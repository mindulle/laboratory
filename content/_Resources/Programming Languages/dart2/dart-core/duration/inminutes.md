[dart:core](../../dart-core/dart-core-library){._links-link}

inMinutes property
==================

::: {#getter .section .multi-line-signature}
[int](../int-class) inMinutes
:::

The number of whole minutes spanned by this
[Duration](../duration-class).

The returned value can be greater than 59. For example, a duration of
three hours and 12 minutes has 192 minutes.

``` {.language-dart data-language="dart"}
const duration = Duration(hours: 3, minutes: 12);
print(duration.inMinutes); // 192
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get inMinutes => _duration ~/ Duration.microsecondsPerMinute;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/inMinutes.html>
:::
