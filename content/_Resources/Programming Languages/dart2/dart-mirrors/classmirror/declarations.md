[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

declarations property
=====================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[Symbol](../../dart-core/symbol-class),
[DeclarationMirror](../declarationmirror-class)\> declarations
:::

Returns an immutable map of the declarations actually given in the class
declaration.

This map includes all regular methods, getters, setters, fields,
constructors and type variables actually declared in the class. Both
static and instance members are included, but no inherited members are
included. The map is keyed by the simple names of the declarations.

This does not include inherited members.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<Symbol, DeclarationMirror> get declarations;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClassMirror/declarations.html>
:::
