[dart:math](../../dart-math/dart-math-library){._links-link}

hashCode property
=================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) hashCode

::: {.features}
override
:::
:::

The hash code for this object.

A hash code is a single integer which represents the state of the object
that affects [operator ==](operator_equals) comparisons.

All objects have hash codes. The default hash code implemented by
[Object](../../dart-core/object-class) represents only the identity of
the object, the same way as the default [operator ==](operator_equals)
implementation only considers objects equal if they are identical (see
[identityHashCode](../../dart-core/identityhashcode)).

If [operator ==](operator_equals) is overridden to use the object state
instead, the hash code must also be changed to represent that state,
otherwise the object cannot be used in hash based data structures like
the default [Set](../../dart-core/set-class) and
[Map](../../dart-core/map-class) implementations.

Hash codes must be the same for objects that are equal to each other
according to [operator ==](operator_equals). The hash code of an object
should only change if the object changes in a way that affects equality.
There are no further requirements for the hash codes. They need not be
consistent between executions of the same program and there are no
distribution guarantees.

Objects that are not equal are allowed to have the same hash code. It is
even technically allowed that all instances have the same hash code, but
if clashes happen too often, it may reduce the efficiency of hash-based
data structures like [HashSet](../../dart-collection/hashset-class) or
[HashMap](../../dart-collection/hashmap-class).

If a subclass overrides [hashCode](hashcode), it should override the
[operator ==](operator_equals) operator as well to maintain consistency.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get hashCode => SystemHash.hash2(x.hashCode, y.hashCode);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/hashCode.html>
:::
