[dart:async](../../dart-async/dart-async-library){._links-link}

isActive property
=================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isActive
:::

Returns whether the timer is still active.

A non-periodic timer is active if the callback has not been executed,
and the timer has not been canceled.

A periodic timer is active if it has not been canceled.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isActive;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Timer/isActive.html>
:::
