[dart:core](../../dart-core/dart-core-library){._links-link}

inMilliseconds property
=======================

::: {#getter .section .multi-line-signature}
[int](../int-class) inMilliseconds
:::

The number of whole milliseconds spanned by this
[Duration](../duration-class).

The returned value can be greater than 999. For example, a duration of
three seconds and 125 milliseconds has 3125 milliseconds.

``` {.language-dart data-language="dart"}
const duration = Duration(seconds: 3, milliseconds: 125);
print(duration.inMilliseconds); // 3125
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get inMilliseconds => _duration ~/ Duration.microsecondsPerMillisecond;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/inMilliseconds.html>
:::
