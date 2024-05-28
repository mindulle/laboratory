[dart:io](../dart-io/dart-io-library){._links-link}

ProcessResult class
===================

The result of running a non-interactive process started with
[Process.run](process/run) or [Process.runSync](process/runsync).

Constructors
------------

[ProcessResult](processresult/processresult)([int](../dart-core/int-class)
pid, [int](../dart-core/int-class) exitCode, dynamic stdout, dynamic
stderr)

Properties {#instance-properties}
----------

[exitCode](processresult/exitcode) → [int](../dart-core/int-class)

::: {.features}
final
:::

Exit code for the process.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[pid](processresult/pid) → [int](../dart-core/int-class)

::: {.features}
final
:::

Process id of the process.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[stderr](processresult/stderr) → dynamic

::: {.features}
final
:::

Standard error from the process. The value used for the `stderrEncoding`
argument to `Process.run` determines the type. If `null` was used, this
value is of type `List<int>` otherwise it is of type `String`.

[stdout](processresult/stdout) → dynamic

::: {.features}
final
:::

Standard output from the process. The value used for the
`stdoutEncoding` argument to `Process.run` determines the type. If
`null` was used, this value is of type `List<int>` otherwise it is of
type `String`.

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessResult-class.html>
:::
