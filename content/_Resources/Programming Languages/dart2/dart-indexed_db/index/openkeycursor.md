[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

openKeyCursor method
====================

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Cursor](../cursor-class)\>
openKeyCursor(

1.  {dynamic key,
2.  [KeyRange](../keyrange-class)? range,
3.  [String](../../dart-core/string-class)? direction,
4.  [bool](../../dart-core/bool-class)? autoAdvance}

)
:::

Creates a stream of cursors over the records in this object store.

See also:

-   [ObjectStore.openCursor](../objectstore/opencursor)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Cursor> openKeyCursor(
    {key, KeyRange? range, String? direction, bool? autoAdvance}) {
  var key_OR_range = null;
  if (key != null) {
    if (range != null) {
      throw new ArgumentError('Cannot specify both key and range.');
    }
    key_OR_range = key;
  } else {
    key_OR_range = range;
  }
  var request;
  if (direction == null) {
    // FIXME: Passing in "next" should be unnecessary.
    request = _openKeyCursor(key_OR_range, "next");
  } else {
    request = _openKeyCursor(key_OR_range, direction);
  }
  return ObjectStore._cursorStreamFromResult(request, autoAdvance);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Index/openKeyCursor.html>
:::
