[dart:html](../../dart-html/dart-html-library){._links-link}

table method
============

::: {.section .multi-line-signature}
void table(

1.  \[[Object](../../dart-core/object-class)? tabularData,
2.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    properties\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void table([Object? tabularData, List<String>? properties]) =>
    _isConsoleDefined
        ? JS('void', 'window.console.table(#, #)', tabularData, properties)
        : null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Console/table.html>
:::
