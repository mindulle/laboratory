[dart:io](../../dart-io/dart-io-library){._links-link}

forEach method
==============

::: {.section .multi-line-signature}
void forEach(

1.  void action(
    1.  [String](../../dart-core/string-class) name,
    2.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
        values

    )

)
:::

Performs the `action` on each header.

The `action` function is called with each header\'s name and a list of
the header\'s values. The casing of the name string is determined by the
last [add](add) or [set](set) operation for that particular header,
which defaults to lower-casing the header name unless explicitly set to
preserve the case.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void forEach(void Function(String name, List<String> values) action);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/forEach.html>
:::
