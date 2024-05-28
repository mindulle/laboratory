[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

transaction method
==================

::: {.section .multi-line-signature}
[Transaction](../transaction-class) transaction(

1.  dynamic storeName\_OR\_storeNames,
2.  [String](../../dart-core/string-class) mode

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Transaction transaction(storeName_OR_storeNames, String mode) {
  if (mode != 'readonly' && mode != 'readwrite') {
    throw new ArgumentError(mode);
  }

  // TODO(sra): Ensure storeName_OR_storeNames is a string or List<String>,
  // and copy to JavaScript array if necessary.

  // Try and create a transaction with a string mode.  Browsers that expect a
  // numeric mode tend to convert the string into a number.  This fails
  // silently, resulting in zero ('readonly').
  return _transaction(storeName_OR_storeNames, mode);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database/transaction.html>
:::
