[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

openCursor method
=================

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[CursorWithValue](../cursorwithvalue-class)\>
openCursor(

1.  {dynamic key,
2.  [KeyRange](../keyrange-class)? range,
3.  [String](../../dart-core/string-class)? direction,
4.  [bool](../../dart-core/bool-class)? autoAdvance}

)
:::

Creates a stream of cursors over the records in this object store.

**The stream must be manually advanced by calling
[Cursor.next](../cursor/next) after each item or by specifying
autoAdvance to be true.**

``` {.language-dart data-language="dart"}
var cursors = objectStore.openCursor().listen(
  (cursor) {
    // ...some processing with the cursor
    cursor.next(); // advance onto the next cursor.
  },
  onDone: () {
    // called when there are no more cursors.
    print('all done!');
  });
```

Asynchronous operations which are not related to the current transaction
will cause the transaction to automatically be committed\-- all
processing must be done synchronously unless they are additional async
requests to the current transaction.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<CursorWithValue> openCursor(
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

  // TODO: try/catch this and return a stream with an immediate error.
  var request;
  if (direction == null) {
    request = _openCursor(key_OR_range);
  } else {
    request = _openCursor(key_OR_range, direction);
  }
  return _cursorStreamFromResult(request, autoAdvance);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/ObjectStore/openCursor.html>
:::
