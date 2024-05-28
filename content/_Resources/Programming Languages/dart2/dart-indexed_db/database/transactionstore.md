[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

transactionStore method
=======================

::: {.section .multi-line-signature}
[Transaction](../transaction-class) transactionStore(

1.  [String](../../dart-core/string-class) storeName,
2.  [String](../../dart-core/string-class) mode

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Transaction transactionStore(String storeName, String mode) {
  if (mode != 'readonly' && mode != 'readwrite') {
    throw new ArgumentError(mode);
  }
  // Try and create a transaction with a string mode.  Browsers that expect a
  // numeric mode tend to convert the string into a number.  This fails
  // silently, resulting in zero ('readonly').
  return _transaction(storeName, mode);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database/transactionStore.html>
:::
