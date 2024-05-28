[dart:core](../../dart-core/dart-core-library){._links-link}

attach method
=============

::: {.section .multi-line-signature}
void attach(

1.  [Object](../object-class) value,
2.  T finalizationToken,
3.  {[Object](../object-class)? detach}

)
:::

Attaches this finalizer to `value`.

When `value` is no longer accessible to the program, while still having
an attachement to this finalizer, the callback of this finalizer *may*
be called with `finalizationToken` as argument. The callback may be
called at most once per active attachment, ones which have not been
detached by calling [Finalizer.detach](detach).

If a non-`null` `detach` value is provided, that object can be passed to
[Finalizer.detach](detach) to remove the attachment again.

The `value` and `detach` arguments do not count towards those objects
being accessible to the program. Both must be objects supported as an
[Expando](../expando-class) key. They may be the *same* object.

Example:

``` {.language-dart data-language="dart"}
class Database {
  // Keeps the finalizer itself reachable, otherwise it might be disposed
  // before the finalizer callback gets a chance to run.
  static final Finalizer<DBConnection> _finalizer =
      Finalizer((connection) => connection.close());

  factory Database.connect() {
    // Wraps the connection in a nice user API,
    // *and* closes connection if the user forgets to.
    final connection = DBConnection.connect();
    final wrapper = Database._fromConnection();
    // Get finalizer callback when `wrapper` is no longer reachable.
    _finalizer.attach(wrapper, connection, detach: wrapper);
    return wrapper;
  }

  Database._fromConnection();

  // Some useful methods.
}
```

Multiple objects may be attached using the same finalization token, and
the finalizer can be attached multiple times to the same object with
different, or the same, finalization token.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void attach(Object value, T finalizationToken, {Object? detach});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Finalizer/attach.html>
:::
