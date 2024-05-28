[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

typeVariables property
======================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[TypeVariableMirror](../typevariablemirror-class)\>
typeVariables
:::

An immutable list with mirrors for all type variables for this type.

If this type is a generic declaration or an invocation of a generic
declaration, the returned list contains mirrors on the type variables
declared in the original declaration. Otherwise, the returned list is
empty.

This list preserves the order of declaration of the type variables.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<TypeVariableMirror> get typeVariables;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/TypeMirror/typeVariables.html>
:::
