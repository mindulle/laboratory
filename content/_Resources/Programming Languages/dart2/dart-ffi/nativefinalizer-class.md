[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

NativeFinalizer class
=====================

A native finalizer which can be attached to Dart objects.

When [attach](nativefinalizer/attach)ed to a Dart object, this
finalizer\'s native callback is called after the Dart object is garbage
collected or becomes inaccessible for other reasons.

Callbacks will happen as early as possible, when the object becomes
inaccessible to the program, and may happen at any moment during
execution of the program. At the latest, when an isolate group shuts
down, this callback is guaranteed to be called for each object in that
isolate group that the finalizer is still attached to.

Compared to the [Finalizer](../dart-core/finalizer-class) from
`dart:core`, which makes no promises to ever call an attached callback,
this native finalizer promises that all attached finalizers are
definitely called at least once before the program ends, and the
callbacks are called as soon as possible after an object is recognized
as inaccessible.

When the callback is a Dart function rather than a native function, use
[Finalizer](../dart-core/finalizer-class) instead.

A native finalizer can be used to close native resources. See the
following example.

``` {.language-dart data-language="dart"}
/// [Database] enables interacting with the native database.
///
/// After [close] is called, cannot be used to [query].
///
/// If a [Database] is garbage collected, it is automatically closed by
/// means of a native finalizer. Prefer closing manually for timely
/// release of native resources.
///
/// Note this class is incomplete and for illustration purposes only.
class Database implements Finalizable {
  /// The native finalizer runs [_closeDatabasePointer] on [_nativeDatabase]
  /// if the object is garbage collected.
  ///
  /// Keeps the finalizer itself reachable, otherwise it might be disposed
  /// before the finalizer callback gets a chance to run.
  static final _finalizer =
      NativeFinalizer(_nativeDatabaseBindings.closeDatabaseAddress.cast());

  /// The native resource.
  ///
  /// Should be closed exactly once with [_closeDatabase] or
  /// [_closeDatabasePointer].
  Pointer<_NativeDatabase> _nativeDatabase;

  /// Used to prevent double close and usage after close.
  bool _closed = false;

  Database._(this._nativeDatabase);

  /// Open a database.
  factory Database.open() {
    final nativeDatabase = _nativeDatabaseBindings.openDatabase();
    final database = Database._(nativeDatabase);
    _finalizer.attach(database, nativeDatabase.cast(), detach: database);
    return database;
  }

  /// Closes this database.
  ///
  /// This database cannot be used anymore after it is closed.
  void close() {
    if (_closed) {
      return;
    }
    _closed = true;
    _finalizer.detach(this);
    _nativeDatabaseBindings.closeDatabase(_nativeDatabase);
  }

  /// Query the database.
  ///
  /// The database should not have been closed.
  void query() {
    if (_closed) {
      throw StateError('The database has been closed.');
    }

    // Query the database.
  }
}

final _nativeDatabaseBindings = _NativeDatabaseLib(DynamicLibrary.process());

// The following classes are typically generated with `package:ffigen`.
// Use `symbol-address` to expose the address of the close function.
class _NativeDatabaseLib {
  final DynamicLibrary _library;

  _NativeDatabaseLib(this._library);

  late final openDatabase = _library.lookupFunction<
      Pointer<_NativeDatabase> Function(),
      Pointer<_NativeDatabase> Function()>('OpenDatabase');
  late final closeDatabaseAddress =
      _library.lookup<NativeFunction<Void Function(Pointer<_NativeDatabase>)>>(
          'CloseDatabase');
  late final closeDatabase = closeDatabaseAddress
      .asFunction<void Function(Pointer<_NativeDatabase>)>();
}

class _NativeDatabase extends Opaque {}
```

Annotations

:   -   \@Since(\'2.17\')

Constructors
------------

[NativeFinalizer](nativefinalizer/nativefinalizer)([Pointer](pointer-class)\<[NativeFinalizerFunction](nativefinalizerfunction)\>
callback)

::: {.constructor-modifier .features}
factory
:::

Creates a finalizer with the given finalization callback.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[attach](nativefinalizer/attach)([Finalizable](finalizable-class) value,
[Pointer](pointer-class)\<[Void](void-class)\> token,
{[Object](../dart-core/object-class)? detach,
[int](../dart-core/int-class)? externalSize}) → void

Attaches this finalizer to `value`.

[detach](nativefinalizer/detach)([Object](../dart-core/object-class)
detach) → void

Detaches this finalizer from values attached with
[detach](nativefinalizer/detach).

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeFinalizer-class.html>
:::
