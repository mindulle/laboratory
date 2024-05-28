[dart:developer](../../dart-developer/dart-developer-library){._links-link}

now property
============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) now
:::

The current time stamp from the clock used by the timeline. Units are
microseconds.

When run on the Dart VM, uses the same monotonic clock as the embedding
API\'s `Dart_TimelineGetMicros`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int get now => _getTraceClock();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Timeline/now.html>
:::
