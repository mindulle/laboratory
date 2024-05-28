[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

isSubtypeOf method
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isSubtypeOf(

1.  [TypeMirror](../typemirror-class) other

)
:::

Checks the subtype relationship, denoted by `<:` in the language
specification.

This is the type relationship used in `is` test checks.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool isSubtypeOf(TypeMirror other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/TypeMirror/isSubtypeOf.html>
:::
