[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

isStatic property
=================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isStatic
:::

Returns `true` if the reflectee is a static variable. Otherwise returns
`false`.

For the purposes of the mirror library, top-level variables are
implicitly declared static.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isStatic;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/VariableMirror/isStatic.html>
:::
