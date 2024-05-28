[dart:io](../../dart-io/dart-io-library){._links-link}

set method
==========

::: {.section .multi-line-signature}
void set(

1.  [String](../../dart-core/string-class) name,
2.  [Object](../../dart-core/object-class) value,
3.  {\@Since(\"2.8\") [bool](../../dart-core/bool-class)
    preserveHeaderCase = false}

)
:::

Sets the header `name` to `value`.

Removes all existing values for the header named `name` and then
[add](add)s `value` to it.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set(String name, Object value,
    {@Since("2.8") bool preserveHeaderCase = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/set.html>
:::
