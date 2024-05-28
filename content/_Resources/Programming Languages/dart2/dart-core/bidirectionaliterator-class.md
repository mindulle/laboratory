[dart:core](../dart-core/dart-core-library){._links-link}

BidirectionalIterator\<E\> class
================================

An [Iterator](iterator-class) that allows moving backwards as well as
forwards.

Deprecation note: This interface has turned out to not be valuable as a
general reusable interface. There is still only one class implementing
it, [RuneIterator](runeiterator-class), and at least one other
bidirectional iterator preferred a different name than `movePrevious`
for the other direction. As such, this interface does not carry its own
weight, and will be removed in a later release.

Implemented types

:   -   [Iterator](iterator-class)\<E\>

Implementers

:   -   [RuneIterator](runeiterator-class)

Annotations

:   -   @[Deprecated](deprecated-class)(\"Use the implementing class
        directly\")

Constructors
------------

[BidirectionalIterator](bidirectionaliterator/bidirectionaliterator)()

Properties {#instance-properties}
----------

[current](iterator/current) → E

::: {.features}
read-only, inherited
:::

The current element.

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

[moveNext](iterator/movenext)() → [bool](bool-class)

::: {.features}
inherited
:::

Advances the iterator to the next element of the iteration.

[movePrevious](bidirectionaliterator/moveprevious)() →
[bool](bool-class)

Move back to the previous element.

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
<https://api.dart.dev/stable/2.18.5/dart-core/BidirectionalIterator-class.html>
:::
