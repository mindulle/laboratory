[dart:io](../dart-io/dart-io-library){._links-link}

FileMode class
==============

The modes in which a [File](file-class) can be opened.

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

[append](filemode/append-constant) → const [FileMode](filemode-class)
:   Mode for opening a file for reading and writing to the end of it.
    The file is created if it does not already exist.
    <div>

    `const FileMode._internal(2)`

    </div>

[read](filemode/read-constant) → const [FileMode](filemode-class)
:   The mode for opening a file only for reading.
    <div>

    `const FileMode._internal(0)`

    </div>

[write](filemode/write-constant) → const [FileMode](filemode-class)
:   Mode for opening a file for reading and writing. The file is
    overwritten if it already exists. The file is created if it does not
    already exist.
    <div>

    `const FileMode._internal(1)`

    </div>

[writeOnly](filemode/writeonly-constant) → const [FileMode](filemode-class)
:   Mode for opening a file for writing *only*. The file is overwritten
    if it already exists. The file is created if it does not already
    exist.
    <div>

    `const FileMode._internal(3)`

    </div>

[writeOnlyAppend](filemode/writeonlyappend-constant) → const [FileMode](filemode-class)
:   Mode for opening a file for writing *only* to the end of it. The
    file is created if it does not already exist.
    <div>

    `const FileMode._internal(4)`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileMode-class.html>
:::
