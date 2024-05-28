[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

isPrivate property
==================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isPrivate
:::

Whether this declaration is library private.

Always returns `false` for a library declaration, otherwise returns
`true` if the declaration\'s name starts with an underscore character
(`_`), and `false` if it doesn\'t.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isPrivate;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/DeclarationMirror/isPrivate.html>
:::
