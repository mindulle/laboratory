[dart:core](../../dart-core/dart-core-library){._links-link}

inMicroseconds property
=======================

::: {#getter .section .multi-line-signature}
[int](../int-class) inMicroseconds
:::

The number of whole microseconds spanned by this
[Duration](../duration-class).

The returned value can be greater than 999999. For example, a duration
of three seconds, 125 milliseconds and 369 microseconds has 3125369
microseconds.

``` {.language-dart data-language="dart"}
const duration = Duration(seconds: 3, milliseconds: 125,
    microseconds: 369);
print(duration.inMicroseconds); // 3125369
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get inMicroseconds => _duration;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/inMicroseconds.html>
:::
