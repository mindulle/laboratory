[dart:core](../../dart-core/dart-core-library){._links-link}

detach method
=============

::: {.section .multi-line-signature}
void detach(

1.  [Object](../object-class) detach

)
:::

Detaches this finalizer from values attached with [detach](detach).

Each attachment between this finalizer and a value, which was created by
calling [attach](attach) with the [detach](detach) object as `detach`
argument, is removed.

If the finalizer was attached multiple times to the same value with
different detachment keys, only those attachments which used
[detach](detach) are removed.

After detaching, an attachment won\'t cause any callbacks to happen if
the object become inaccessible.

Example:

``` {.language-dart data-language="dart"}
class Database {
  // Keeps the finalizer itself reachable, otherwise it might be disposed
  // before the finalizer callback gets a chance to run.
  static final Finalizer<DBConnection> _finalizer =
      Finalizer((connection) => connection.close());

  final DBConnection _connection;

  Database._fromConnection(this._connection);

  void close() {
    // User requested close.
    _connection.close();
    // Detach from finalizer, no longer needed.
    // Was attached using this object as `detach` token.
    _finalizer.detach(this);
  }

  // Some useful methods.
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void detach(Object detach);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Finalizer/detach.html>
:::
