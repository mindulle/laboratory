[dart:core](../../dart-core/dart-core-library){._links-link}

isAccessor property
===================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isAccessor
:::

Whether the invocation was a getter or a setter call.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isAccessor => isGetter || isSetter;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Invocation/isAccessor.html>
:::
