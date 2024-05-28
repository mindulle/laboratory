[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

isOriginalDeclaration property
==============================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isOriginalDeclaration
:::

Is this the original declaration of this type?

For most classes, they are their own original declaration. For generic
classes, however, there is a distinction between the original class
declaration, which has unbound type variables, and the instantiations of
generic classes, which have bound type variables.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isOriginalDeclaration;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/TypeMirror/isOriginalDeclaration.html>
:::
