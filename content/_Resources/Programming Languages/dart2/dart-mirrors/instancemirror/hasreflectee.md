[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

hasReflectee property
=====================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) hasReflectee
:::

Whether [reflectee](reflectee) will return the instance reflected by
this mirror.

This will always be true in the local case (reflecting instances in the
same isolate), but only true in the remote case if this mirror reflects
a simple value.

A value is simple if one of the following holds:

-   the value is `null`
-   the value is of type [num](../../dart-core/num-class)
-   the value is of type [bool](../../dart-core/bool-class)
-   the value is of type [String](../../dart-core/string-class)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get hasReflectee;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/InstanceMirror/hasReflectee.html>
:::
