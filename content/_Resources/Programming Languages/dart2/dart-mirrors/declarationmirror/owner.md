[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

owner property
==============

::: {#getter .section .multi-line-signature}
[DeclarationMirror](../declarationmirror-class)? owner
:::

A mirror on the owner of this Dart language entity.

The owner is the declaration immediately surrounding the reflectee:

-   For a library, the owner is `null`.
-   For a class declaration, typedef or top level function or variable,
    the owner is the enclosing library.
-   For a mixin application `S with M`, the owner is the owner of `M`.
-   For a constructor, the owner is the immediately enclosing class.
-   For a method, instance variable or a static variable, the owner is
    the immediately enclosing class, unless the class is a mixin
    application `S with M`, in which case the owner is `M`. Note that
    `M` may be an invocation of a generic.
-   For a parameter, local variable or local function the owner is the
    immediately enclosing function.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DeclarationMirror? get owner;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/DeclarationMirror/owner.html>
:::
