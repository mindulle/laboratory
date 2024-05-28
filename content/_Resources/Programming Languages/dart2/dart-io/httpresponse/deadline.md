[dart:io](../../dart-io/dart-io-library){._links-link}

deadline property
=================

::: {.section .multi-line-signature}
[Duration](../../dart-core/duration-class)? deadline

::: {.features}
read / write
:::
:::

Set and get the [deadline](deadline) for the response. The deadline is
timed from the time it\'s set. Setting a new deadline will override any
previous deadline. When a deadline is exceeded, the response will be
closed and any further data ignored.

To disable a deadline, set the [deadline](deadline) to `null`.

The [deadline](deadline) is `null` by default.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration? deadline;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpResponse/deadline.html>
:::
