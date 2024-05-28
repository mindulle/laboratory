[dart:io](../dart-io/dart-io-library){._links-link}

ProcessException class
======================

Implemented types

:   -   [IOException](ioexception-class)

Constructors
------------

[ProcessException](processexception/processexception)([String](../dart-core/string-class)
executable,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>
arguments, \[[String](../dart-core/string-class) message = \"\",
[int](../dart-core/int-class) errorCode = 0\])

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[arguments](processexception/arguments) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

::: {.features}
final
:::

The arguments provided for the process.

[errorCode](processexception/errorcode) → [int](../dart-core/int-class)

::: {.features}
final
:::

The OS error code for the process exception, if any.

[executable](processexception/executable) →
[String](../dart-core/string-class)

::: {.features}
final
:::

The executable provided for the process.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](processexception/message) →
[String](../dart-core/string-class)

::: {.features}
final
:::

The system message for the process exception, if any.

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

[toString](processexception/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
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
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessException-class.html>
:::
