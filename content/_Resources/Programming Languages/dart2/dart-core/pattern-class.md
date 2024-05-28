[dart:core](../dart-core/dart-core-library){._links-link}

Pattern class
=============

An interface for basic searches within strings.

Implementers

:   -   [RegExp](regexp-class)
    -   [String](string-class)

Constructors
------------

[Pattern](pattern/pattern)()

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[allMatches](pattern/allmatches)([String](string-class) string,
\[[int](int-class) start = 0\]) →
[Iterable](iterable-class)\<[Match](match-class)\>

Matches this pattern against the string repeatedly.

[matchAsPrefix](pattern/matchasprefix)([String](string-class) string,
\[[int](int-class) start = 0\]) → [Match](match-class)?

Matches this pattern against the start of `string`.

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
<https://api.dart.dev/stable/2.18.5/dart-core/Pattern-class.html>
:::
