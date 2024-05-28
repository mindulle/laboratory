[dart:math](../dart-math/dart-math-library){._links-link}

Random class
============

A generator of random bool, int, or double values.

The default implementation supplies a stream of pseudo-random bits that
are not suitable for cryptographic purposes.

Use the [Random.secure](random-class) constructor for cryptographic
purposes.

To create a non-negative random integer uniformly distributed in the
range from 0, inclusive, to max, exclusive, use [nextInt(int
max)](random/nextint).

``` {.language-dart data-language="dart"}
var intValue = Random().nextInt(10); // Value is >= 0 and < 10.
intValue = Random().nextInt(100) + 50; // Value is >= 50 and < 150.
```

To create a non-negative random floating point value uniformly
distributed in the range from 0.0, inclusive, to 1.0, exclusive, use
[nextDouble](random/nextdouble).

``` {.language-dart data-language="dart"}
var doubleValue = Random().nextDouble(); // Value is >= 0.0 and < 1.0.
doubleValue = Random().nextDouble() * 256; // Value is >= 0.0 and < 256.0.
```

To create a random Boolean value, use [nextBool](random/nextbool).

``` {.language-dart data-language="dart"}
var boolValue = Random().nextBool(); // true or false, with equal chance.
```

Constructors
------------

[Random](random/random)(\[[int](../dart-core/int-class)? seed\])

::: {.constructor-modifier .features}
factory
:::

Creates a random number generator.

[Random.secure](random/random.secure)()

::: {.constructor-modifier .features}
factory
:::

Creates a cryptographically secure random number generator.

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

[nextBool](random/nextbool)() → [bool](../dart-core/bool-class)

Generates a random boolean value.

[nextDouble](random/nextdouble)() → [double](../dart-core/double-class)

Generates a non-negative random floating point value uniformly
distributed in the range from 0.0, inclusive, to 1.0, exclusive.

[nextInt](random/nextint)([int](../dart-core/int-class) max) →
[int](../dart-core/int-class)

Generates a non-negative random integer uniformly distributed in the
range from 0, inclusive, to `max`, exclusive.

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
<https://api.dart.dev/stable/2.18.5/dart-math/Random-class.html>
:::
