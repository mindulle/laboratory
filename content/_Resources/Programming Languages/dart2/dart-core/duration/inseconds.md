[dart:core](../../dart-core/dart-core-library){._links-link}

inSeconds property
==================

::: {#getter .section .multi-line-signature}
[int](../int-class) inSeconds
:::

The number of whole seconds spanned by this
[Duration](../duration-class).

The returned value can be greater than 59. For example, a duration of
three minutes and 12 seconds has 192 seconds.

``` {.language-dart data-language="dart"}
const duration = Duration(minutes: 3, seconds: 12);
print(duration.inSeconds); // 192
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get inSeconds => _duration ~/ Duration.microsecondsPerSecond;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/inSeconds.html>
:::
