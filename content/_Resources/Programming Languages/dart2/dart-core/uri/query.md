[dart:core](../../dart-core/dart-core-library){._links-link}

query property
==============

::: {#getter .section .multi-line-signature}
[String](../string-class) query
:::

The query component.

The value is the actual substring of the URI representing the query
part, and it is encoded where necessary. To get direct access to the
decoded query, use [queryParameters](queryparameters).

The value is the empty string if there is no query component.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get query;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/query.html>
:::
