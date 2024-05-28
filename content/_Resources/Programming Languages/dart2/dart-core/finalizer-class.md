[dart:core](../dart-core/dart-core-library){._links-link}

Finalizer\<T\> class
====================

A finalizer which can be attached to Dart objects.

A finalizer can create attachments between the finalizer and any number
of Dart values, by calling [attach](finalizer/attach) with the value,
along with a *finalization token* and an optional *attach key*, which
are part of the attachment.

When a Dart value becomes inaccessible to the program, any finalizer
that currently has an attachment to the value *may* have its callback
function called with the attachment\'s finalization token.

Example:

``` {.language-dart data-language="dart"}
class Database {
  // Keeps the finalizer itself reachable, otherwise it might be disposed
  // before the finalizer callback gets a chance to run.
  static final Finalizer<DBConnection> _finalizer =
      Finalizer((connection) => connection.close());

  final DBConnection _connection;

  Database._fromConnection(this._connection);

  factory Database.connect() {
    // Wraps the connection in a nice user API,
    // *and* closes connection if the user forgets to.
    final connection = DBConnection.connect();
    final wrapper = Database._fromConnection(connection);
    // Get finalizer callback when `wrapper` is no longer reachable.
    _finalizer.attach(wrapper, connection, detach: wrapper);
    return wrapper;
  }

  void close() {
    // User requested close.
    _connection.close();
    // Detach from finalizer, no longer needed.
    _finalizer.detach(this);
  }

  // Some useful methods.
}
```

This example has an example of an external resource that needs clean-up.
The finalizer is used to clean up an external connection when the user
of the API no longer has access to that connection. The example uses the
same object as attached object and detach key, which is a useful
approach when each attached object can be detached individually. Being a
detachment key doesn\'t keep an object alive.

No promises are made that the callback will ever be called. The only
thing that is guaranteed is that if a finalizer\'s callback is called
with a specific finalization token as argument, then at least one value
with an attachment to the finalizer that has that finalization token, is
no longer accessible to the program.

If the finalizer *itself* becomes unreachable, it\'s allowed to be
garbage collected and then it won\'t trigger any further callbacks.
Always make sure to keep the finalizer itself reachable while it\'s
needed.

If multiple finalizers are attached to a single object, or the same
finalizer is attached multiple times to an object, and that object
becomes inaccessible to the program, then any number (including zero) of
those attachments may trigger their associated finalizer\'s callback. It
will not necessarily be all or none of them.

Finalization callbacks will happen as *events*. They will not happen
during execution of other code, and not as a microtask, but as
high-level events similar to timer events.

Finalization callbacks must not throw.

When running on the Dart native runtime, and the callback is a native
function rather than a Dart function, use `dart:ffi`\'s
[NativeFinalizer](../dart-ffi/nativefinalizer-class) instead.

Annotations

:   -   \@Since(\"2.17\")

Constructors
------------

[Finalizer](finalizer/finalizer)(void callback(T))

::: {.constructor-modifier .features}
factory
:::

Creates a finalizer with the given finalization callback.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[attach](finalizer/attach)([Object](object-class) value, T
finalizationToken, {[Object](object-class)? detach}) → void

Attaches this finalizer to `value`.

[detach](finalizer/detach)([Object](object-class) detach) → void

Detaches this finalizer from values attached with
[detach](finalizer/detach).

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Finalizer-class.html>
:::
