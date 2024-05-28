[dart:collection](../../dart-collection/dart-collection-library){._links-link}

mapToString method
==================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) mapToString(

1.  [Map](../../dart-core/map-class)\<[Object](../../dart-core/object-class)?,
    [Object](../../dart-core/object-class)?\> m

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String mapToString(Map<Object?, Object?> m) {
  // Reuses the list in IterableBase for detecting toString cycles.
  if (_isToStringVisiting(m)) {
    return '{...}';
  }

  var result = StringBuffer();
  try {
    _toStringVisiting.add(m);
    result.write('{');
    bool first = true;
    m.forEach((Object? k, Object? v) {
      if (!first) {
        result.write(', ');
      }
      first = false;
      result.write(k);
      result.write(': ');
      result.write(v);
    });
    result.write('}');
  } finally {
    assert(identical(_toStringVisiting.last, m));
    _toStringVisiting.removeLast();
  }

  return result.toString();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapBase/mapToString.html>
:::
