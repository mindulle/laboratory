[dart:io](../dart-io/dart-io-library){._links-link}

OSError class
=============

An [Exception](../dart-core/exception-class) holding information about
an error from the operating system.

Implemented types

:   -   [Exception](../dart-core/exception-class)

Constructors
------------

[OSError](oserror/oserror)(\[[String](../dart-core/string-class) message
= \"\", [int](../dart-core/int-class) errorCode = noErrorCode\])

::: {.constructor-modifier .features}
const
:::

Creates an OSError object from a message and an errorCode.

Properties {#instance-properties}
----------

[errorCode](oserror/errorcode) → [int](../dart-core/int-class)

::: {.features}
final
:::

Error code supplied by the operating system.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](oserror/message) → [String](../dart-core/string-class)

::: {.features}
final
:::

Error message supplied by the operating system. This will be empty if no
message is associated with the error.

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

[toString](oserror/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

Converts an OSError object to a string representation.

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

[noErrorCode](oserror/noerrorcode-constant) → const [int](../dart-core/int-class)
:   Constant used to indicate that no OS error code is available.
    <div>

    `-1`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/OSError-class.html>
:::
