[dart:io](../dart-io/dart-io-library){._links-link}

ProcessStartMode class
======================

Modes for running a new process.

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

[toString](processstartmode/tostring)() →
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

Static Properties
-----------------

[values](processstartmode/values) →
[List](../dart-core/list-class)\<[ProcessStartMode](processstartmode-class)\>

::: {.features}
read-only
:::

Constants
---------

[detached](processstartmode/detached-constant) → const [ProcessStartMode](processstartmode-class)
:   Detached child process with no open communication channel.
    <div>

    `const ProcessStartMode._internal(2)`

    </div>

[detachedWithStdio](processstartmode/detachedwithstdio-constant) → const [ProcessStartMode](processstartmode-class)
:   Detached child process with stdin, stdout and stderr still open for
    communication with the child.
    <div>

    `const ProcessStartMode._internal(3)`

    </div>

[inheritStdio](processstartmode/inheritstdio-constant) → const [ProcessStartMode](processstartmode-class)
:   Stdio handles are inherited by the child process.
    <div>

    `const ProcessStartMode._internal(1)`

    </div>

[normal](processstartmode/normal-constant) → const [ProcessStartMode](processstartmode-class)
:   Normal child process.
    <div>

    `const ProcessStartMode._internal(0)`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessStartMode-class.html>
:::
