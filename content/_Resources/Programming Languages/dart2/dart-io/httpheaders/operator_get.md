[dart:io](../../dart-io/dart-io-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
operator \[\](

1.  [String](../../dart-core/string-class) name

)
:::

The values for the header named `name`.

Returns null if there is no header with the provided name, otherwise
returns a new list containing the current values. Not that modifying the
list does not change the header.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<String>? operator [](String name);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/operator_get.html>
:::
