[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

location property
=================

::: {#getter .section .multi-line-signature}
[SourceLocation](../sourcelocation-class)? location
:::

The source location of this Dart language entity, or `null` if the
entity is synthetic.

If the reflectee is a variable, the returned location gives the position
of the variable name at its point of declaration.

If the reflectee is a library, class, typedef, function or type variable
with associated metadata, the returned location gives the position of
the first metadata declaration associated with the reflectee.

Otherwise:

If the reflectee is a library, the returned location gives the position
of the keyword \'library\' at the reflectee\'s point of declaration, if
the reflectee is a named library, or the first character of the first
line in the compilation unit defining the reflectee if the reflectee is
anonymous.

If the reflectee is an abstract class, the returned location gives the
position of the keyword \'abstract\' at the reflectee\'s point of
declaration. Otherwise, if the reflectee is a class, the returned
location gives the position of the keyword \'class\' at the reflectee\'s
point of declaration.

If the reflectee is a typedef the returned location gives the position
of the of the keyword \'typedef\' at the reflectee\'s point of
declaration.

If the reflectee is a function with a declared return type, the returned
location gives the position of the function\'s return type at the
reflectee\'s point of declaration. Otherwise. the returned location
gives the position of the function\'s name at the reflectee\'s point of
declaration.

This operation is optional and may throw an
[UnsupportedError](../../dart-core/unsupportederror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
SourceLocation? get location;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/DeclarationMirror/location.html>
:::
