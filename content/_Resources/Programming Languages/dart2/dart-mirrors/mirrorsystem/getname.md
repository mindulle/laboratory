[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

getName method
==============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) getName(

1.  [Symbol](../../dart-core/symbol-class) symbol

)
:::

Returns the name of `symbol`.

The following text is non-normative:

Using this method may result in larger output. If possible, use
[MirrorsUsed](../mirrorsused-class){.deprecated} to specify which
symbols must be retained in clear text.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static String getName(Symbol symbol);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorSystem/getName.html>
:::
