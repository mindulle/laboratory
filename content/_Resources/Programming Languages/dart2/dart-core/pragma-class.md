[dart:core](../dart-core/dart-core-library){._links-link}

pragma class
============

A hint to tools.

Tools that work with Dart programs may accept hints to guide their
behavior as `pragma` annotations on declarations. Each tool decides
which hints it accepts, what they mean, and whether and how they apply
to sub-parts of the annotated entity.

Tools that recognize pragma hints should pick a pragma prefix to
identify the tool. They should recognize any hint with a
[name](pragma/name) starting with their prefix followed by `:` as if it
was intended for that tool. A hint with a prefix for another tool should
be ignored (unless compatibility with that other tool is a goal).

A tool may recognize unprefixed names as well, if they would recognize
that name with their own prefix in front.

If the hint can be parameterized, an extra [options](pragma/options)
object can be added as well.

For example:

``` {.language-dart data-language="dart"}
@pragma('Tool:pragma-name', [param1, param2, ...])
class Foo { }

@pragma('OtherTool:other-pragma')
void foo() { }
```

Here class `Foo` is annotated with a Tool specific pragma
\'pragma-name\' and function `foo` is annotated with a pragma
\'other-pragma\' specific to OtherTool.

Constructors
------------

[pragma](pragma/pragma)([String](string-class) name,
\[[Object](object-class)? options\])

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Creates a hint named `name` with optional `options`.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[name](pragma/name) → [String](string-class)

::: {.features}
final
:::

The name of the hint.

[options](pragma/options) → [Object](object-class)?

::: {.features}
final
:::

Optional extra data parameterizing the hint.

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

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/pragma-class.html>
:::
