[dart:core](../dart-core/dart-core-library){._links-link}

RuneIterator class
==================

[Iterator](iterator-class) for reading runes (integer Unicode code
points) of a Dart string.

Implemented types

:   -   [BidirectionalIterator](bidirectionaliterator-class){.deprecated}\<[int](int-class)\>

Constructors
------------

[RuneIterator](runeiterator/runeiterator)([String](string-class) string)
:   Create an iterator positioned at the beginning of the string.

[RuneIterator.at](runeiterator/runeiterator.at)([String](string-class) string, [int](int-class) index)
:   Create an iterator positioned before the `index`th code unit of the
    string.

Properties {#instance-properties}
----------

[current](runeiterator/current) → [int](int-class)

::: {.features}
read-only, override
:::

The rune (integer Unicode code point) starting at the current position
in the string.

[currentAsString](runeiterator/currentasstring) → [String](string-class)

::: {.features}
read-only
:::

A string containing the current rune.

[currentSize](runeiterator/currentsize) → [int](int-class)

::: {.features}
read-only
:::

The number of code units comprising the current rune.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[rawIndex](runeiterator/rawindex) ↔ [int](int-class)

::: {.features}
read / write
:::

The starting position of the current rune in the string.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[string](runeiterator/string) → [String](string-class)

::: {.features}
final
:::

String being iterated.

Methods {#instance-methods}
-------

[moveNext](runeiterator/movenext)() → [bool](bool-class)

::: {.features}
override
:::

Advances the iterator to the next element of the iteration.

[movePrevious](runeiterator/moveprevious)() → [bool](bool-class)

::: {.features}
override
:::

Move back to the previous element.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reset](runeiterator/reset)(\[[int](int-class) rawIndex = 0\]) → void

Resets the iterator to the given index into the string.

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
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator-class.html>
:::
