[dart:io](../dart-io/dart-io-library){._links-link}

FileLock class
==============

Type of lock when requesting a lock on a file.

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

Constants
---------

[blockingExclusive](filelock/blockingexclusive-constant) → const [FileLock](filelock-class)
:   Blocking exclusive file lock.
    <div>

    `const FileLock._internal(4)`

    </div>

[blockingShared](filelock/blockingshared-constant) → const [FileLock](filelock-class)
:   Blocking shared file lock.
    <div>

    `const FileLock._internal(3)`

    </div>

[exclusive](filelock/exclusive-constant) → const [FileLock](filelock-class)
:   Exclusive file lock.
    <div>

    `const FileLock._internal(2)`

    </div>

[shared](filelock/shared-constant) → const [FileLock](filelock-class)
:   Shared file lock.
    <div>

    `const FileLock._internal(1)`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileLock-class.html>
:::
