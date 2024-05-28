[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

createObjectStore method
========================

::: {.section .multi-line-signature}
[ObjectStore](../objectstore-class) createObjectStore(

1.  [String](../../dart-core/string-class) name,
2.  {dynamic keyPath,
3.  [bool](../../dart-core/bool-class)? autoIncrement}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ObjectStore createObjectStore(String name, {keyPath, bool? autoIncrement}) {
  var options = {};
  if (keyPath != null) {
    options['keyPath'] = keyPath;
  }
  if (autoIncrement != null) {
    options['autoIncrement'] = autoIncrement;
  }

  return _createObjectStore(name, options);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database/createObjectStore.html>
:::
