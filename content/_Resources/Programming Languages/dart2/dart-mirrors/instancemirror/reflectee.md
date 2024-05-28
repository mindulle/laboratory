[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

reflectee property
==================

::: {#getter .section .multi-line-signature}
dynamic reflectee
:::

If the [InstanceMirror](../instancemirror-class) reflects an instance it
is meaningful to have a local reference to, we provide access to the
actual instance here.

If you access [reflectee](reflectee) when [hasReflectee](hasreflectee)
is false, an exception is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
dynamic get reflectee;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/InstanceMirror/reflectee.html>
:::
