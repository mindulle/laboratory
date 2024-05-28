[dart:core](../../dart-core/dart-core-library){._links-link}

secondsPerMinute constant
=========================

::: {.section .multi-line-signature}
[int](../int-class) const secondsPerMinute
:::

The number of seconds per minute.

Notice that some minutes of official clock time might differ in length
because of leap seconds. The [Duration](../duration-class) and
[DateTime](../datetime-class) classes ignore leap seconds and consider
all minutes to have 60 seconds.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const int secondsPerMinute = 60;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/secondsPerMinute-constant.html>
:::
