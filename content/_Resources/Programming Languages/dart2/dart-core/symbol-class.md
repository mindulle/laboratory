[dart:core](../dart-core/dart-core-library){._links-link}

Symbol class
============

Opaque name used by mirrors, invocations and
[Function.apply](function/apply).

Constructors
------------

[Symbol](symbol/symbol)([String](string-class) name)

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Constructs a new [Symbol](symbol-class) representing the provided name.

Properties {#instance-properties}
----------

[hashCode](symbol/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

Returns a hash code compatible with
[operator==](symbol/operator_equals).

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

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](symbol/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Symbols are equal to other symbols with an equal (`==`) name string.

Constants
---------

[empty](symbol/empty-constant) → const [Symbol](symbol-class)
:   The empty symbol.
    <div>

    `Symbol("")`

    </div>

[unaryMinus](symbol/unaryminus-constant) → const [Symbol](symbol-class)
:   The symbol corresponding to the name of the unary minus operator.
    <div>

    `Symbol("unary-")`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Symbol-class.html>
:::
