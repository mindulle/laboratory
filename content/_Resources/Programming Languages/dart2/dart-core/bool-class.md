[dart:core](../dart-core/dart-core-library){._links-link}

bool class
==========

The reserved words `true` and `false` denote objects that are the only
two instances of this class.

It is a compile-time error for a class to attempt to extend or implement
bool.

Constructors
------------

[bool.fromEnvironment](bool/bool.fromenvironment)([String](string-class)
name, {[bool](bool-class) defaultValue = false})

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Returns the boolean value of the environment declaration `name`.

[bool.hasEnvironment](bool/bool.hasenvironment)([String](string-class)
name)

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Whether there is an environment declaration `name`.

Properties {#instance-properties}
----------

[hashCode](bool/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](bool/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns either `"true"` for `true` and `"false"` for `false`.

Operators
---------

[operator &](bool/operator_bitwise_and)([bool](bool-class) other) →
[bool](bool-class)

::: {.features}
\@Since(\"2.1\")
:::

The logical conjunction (\"and\") of this and `other`.

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator \^](bool/operator_bitwise_exclusive_or)([bool](bool-class)
other) → [bool](bool-class)

::: {.features}
\@Since(\"2.1\")
:::

The logical exclusive disjunction (\"exclusive or\") of this and
`other`.

[operator \|](bool/operator_bitwise_or)([bool](bool-class) other) →
[bool](bool-class)

::: {.features}
\@Since(\"2.1\")
:::

The logical disjunction (\"inclusive or\") of this and `other`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/bool-class.html>
:::
