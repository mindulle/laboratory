[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

transactionStores method
========================

::: {.section .multi-line-signature}
[Transaction](../transaction-class) transactionStores(

1.  [DomStringList](../../dart-html/domstringlist-class) storeNames,
2.  [String](../../dart-core/string-class) mode

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Transaction transactionStores(DomStringList storeNames, String mode) {
  if (mode != 'readonly' && mode != 'readwrite') {
    throw new ArgumentError(mode);
  }
  return _transaction(storeNames, mode);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database/transactionStores.html>
:::
