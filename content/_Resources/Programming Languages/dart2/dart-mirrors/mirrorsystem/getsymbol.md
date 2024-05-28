[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

getSymbol method
================

::: {.section .multi-line-signature}
[Symbol](../../dart-core/symbol-class) getSymbol(

1.  [String](../../dart-core/string-class) name,
2.  \[[LibraryMirror](../librarymirror-class)? library\]

)
:::

Returns a symbol for `name`.

If `library` is not a [LibraryMirror](../librarymirror-class) or if
`name` is a private identifier and `library` is `null`, throws an
[ArgumentError](../../dart-core/argumenterror-class). If `name` is a
private identifier, the symbol returned is with respect to `library`.

The following text is non-normative:

Using this method may result in larger output. If possible, use the
const constructor of [Symbol](../../dart-core/symbol-class) or symbol
literals.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Symbol getSymbol(String name, [LibraryMirror? library]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorSystem/getSymbol.html>
:::
