[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

isStatic property
=================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isStatic
:::

A function is considered non-static iff it is permited to refer to
\'this\'.

Note that generative constructors are considered non-static, whereas
factory constructors are considered static.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isStatic;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MethodMirror/isStatic.html>
:::
