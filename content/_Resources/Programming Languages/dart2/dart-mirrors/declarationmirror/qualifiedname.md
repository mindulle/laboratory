[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

qualifiedName property
======================

::: {#getter .section .multi-line-signature}
[Symbol](../../dart-core/symbol-class) qualifiedName
:::

The fully-qualified name for this Dart language entity.

This name is qualified by the name of the owner. For instance, the
qualified name of a method \'method\' in class \'Class\' in library
\'library\' is \'library.Class.method\'.

Returns a [Symbol](../../dart-core/symbol-class) constructed from a
string representing the fully qualified name of the reflectee. Let *o*
be the [owner](owner) of this mirror, let *r* be the reflectee of this
mirror, let *p* be the fully qualified name of the reflectee of *o*, and
let *s* be the simple name of *r* computed by [simpleName](simplename).
The fully qualified name of *r* is the concatenation of *p*, \'.\', and
*s*.

Because an isolate can contain more than one library with the same name
(at different URIs), a fully-qualified name does not uniquely identify
any language entity.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Symbol get qualifiedName;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/DeclarationMirror/qualifiedName.html>
:::
