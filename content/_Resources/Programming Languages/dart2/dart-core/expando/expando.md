[dart:core](../../dart-core/dart-core-library){._links-link}

Expando\<T extends Object\> constructor
=======================================

::: {.section .multi-line-signature}
Expando\<T extends Object\>(

1.  \[[String](../string-class)? name\]

)
:::

Creates a new [Expando](../expando-class). The optional name is only
used for debugging purposes and creating two different
[Expando](../expando-class)s with the same name yields two
[Expando](../expando-class)s that work on different properties of the
objects they are used on.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Expando([String? name]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Expando/Expando.html>
:::
