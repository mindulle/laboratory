[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

createIndex method
==================

::: {.section .multi-line-signature}
[Index](../index-class) createIndex(

1.  [String](../../dart-core/string-class) name,
2.  dynamic keyPath,
3.  {[bool](../../dart-core/bool-class)? unique,
4.  [bool](../../dart-core/bool-class)? multiEntry}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Index createIndex(String name, keyPath, {bool? unique, bool? multiEntry}) {
  var options = {};
  if (unique != null) {
    options['unique'] = unique;
  }
  if (multiEntry != null) {
    options['multiEntry'] = multiEntry;
  }

  return _createIndex(name, keyPath, options);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/ObjectStore/createIndex.html>
:::
