[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

transactionList method
======================

::: {.section .multi-line-signature}
[Transaction](../transaction-class) transactionList(

1.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    storeNames,
2.  [String](../../dart-core/string-class) mode

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Transaction transactionList(List<String> storeNames, String mode) {
  if (mode != 'readonly' && mode != 'readwrite') {
    throw new ArgumentError(mode);
  }
  List storeNames_1 = convertDartToNative_StringArray(storeNames);
  return _transaction(storeNames_1, mode);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database/transactionList.html>
:::
