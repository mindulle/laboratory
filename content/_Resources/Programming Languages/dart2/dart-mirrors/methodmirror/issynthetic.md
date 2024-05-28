[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

isSynthetic property
====================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isSynthetic
:::

Returns true if the reflectee is synthetic, and returns false otherwise.

A reflectee is synthetic if it is a getter or setter implicitly
introduced for a field or Type, or if it is a constructor that was
implicitly introduced as a default constructor or as part of a mixin
application.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isSynthetic;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MethodMirror/isSynthetic.html>
:::
