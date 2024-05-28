[dart:core](../dart-core/dart-core-library){._links-link}

Comparable\<T\> class
=====================

Interface used by types that have an intrinsic ordering.

The [compareTo](comparable/compareto) operation defines a total ordering
of objects, which can be used for ordering and sorting.

The [Comparable](comparable-class) interface should be used for the
natural ordering of a type. If a type can be ordered in more than one
way, and none of them is the obvious natural ordering, then it might be
better not to use the [Comparable](comparable-class) interface, and to
provide separate [Comparator](comparator)s instead.

It is recommended that the order of a [Comparable](comparable-class)
agrees with its operator [operator ==](object/operator_equals) equality
(`a.compareTo(b) == 0` iff `a == b`), but this is not a requirement. For
example, [double](double-class) and [DateTime](datetime-class) have
`compareTo` methods that do not agree with operator [operator
==](object/operator_equals). For doubles the
[compareTo](comparable/compareto) method is more precise than the
equality, and for [DateTime](datetime-class) it is less precise.

Examples:

``` {.language-dart data-language="dart"}
(0.0).compareTo(-0.0);   // => 1
0.0 == -0.0;             // => true
var now = DateTime.now();
var utcNow = now.toUtc();
now == utcNow;           // => false
now.compareTo(utcNow);   // => 0
```

The [Comparable](comparable-class) interface does not imply the
existence of the comparison operators `<`, `<=`, `>` and `>=`. These
should only be defined if the ordering is a less-than/greater-than
ordering, that is, an ordering where you would naturally use the words
\"less than\" about the order of two elements.

If the equality operator and [compareTo](comparable/compareto) disagree,
the comparison operators should follow the equality operator, and will
likely also disagree with [compareTo](comparable/compareto). Otherwise
they should match the [compareTo](comparable/compareto) method, so that
`a < b` iff `a.compareTo(b) < 0`.

The [double](double-class) class defines comparison operators that are
compatible with equality. The operators differ from
[double.compareTo](num/compareto) on -0.0 and NaN.

The [DateTime](datetime-class) class has no comparison operators,
instead it has the more precisely named
[DateTime.isBefore](datetime/isbefore) and
[DateTime.isAfter](datetime/isafter), which both agree with
[DateTime.compareTo](datetime/compareto).

Implementers

:   -   [BigInt](bigint-class)
    -   [DateTime](datetime-class)
    -   [Duration](duration-class)
    -   [num](num-class)
    -   [String](string-class)

Constructors
------------

[Comparable](comparable/comparable)()

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

[compareTo](comparable/compareto)(T other) → [int](int-class)

Compares this object to another object.

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

Static Methods
--------------

[compare](comparable/compare)([Comparable](comparable-class) a, [Comparable](comparable-class) b) → [int](int-class)
:   A [Comparator](comparator) that compares one comparable to another.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Comparable-class.html>
:::
