[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

typeArguments property
======================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[TypeMirror](../typemirror-class)\>
typeArguments
:::

An immutable list with mirrors for all type arguments for this type.

If the reflectee is an invocation of a generic class, the type arguments
are the bindings of its type parameters. If the reflectee is the
original declaration of a generic, it has no type arguments and this
method returns an empty list. If the reflectee is not generic, then it
has no type arguments and this method returns an empty list.

This list preserves the order of declaration of the type variables.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<TypeMirror> get typeArguments;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/TypeMirror/typeArguments.html>
:::
