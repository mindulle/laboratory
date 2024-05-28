[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

declarations property
=====================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[Symbol](../../dart-core/symbol-class),
[DeclarationMirror](../declarationmirror-class)\> declarations
:::

Returns an immutable map of the declarations actually given in the
library.

This map includes all regular methods, getters, setters, fields, classes
and typedefs actually declared in the library. The map is keyed by the
simple names of the declarations.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<Symbol, DeclarationMirror> get declarations;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/LibraryMirror/declarations.html>
:::
