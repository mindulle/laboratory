[dart:core](../dart-core/dart-core-library){._links-link}

Runes class
===========

The runes (integer Unicode code points) of a [String](string-class).

The characters of a string are encoded in UTF-16. Decoding UTF-16, which
combines surrogate pairs, yields Unicode code points. Following a
similar terminology to Go, Dart uses the name \'rune\' for an integer
representing a Unicode code point. Use the `runes` property to get the
runes of a string.

Example:

``` {.language-dart data-language="dart"}
const string = 'Dart';
final runes = string.runes.toList();
print(runes); // [68, 97, 114, 116]
```

For a character outside the Basic Multilingual Plane (plane 0) that is
composed of a surrogate pair, runes combines the pair and returns a
single integer.

For example, the Unicode character for \"Man\" emoji (\'👨\', `U+1F468`)
is combined from the surrogates `U+d83d` and `U+dc68`.

Example:

``` {.language-dart data-language="dart"}
const emojiMan = '👨';
print(emojiMan.runes); // (128104)

// Surrogate pairs:
for (final item in emojiMan.codeUnits) {
  print(item.toRadixString(16));
  // d83d
  // dc68
}
```

**See also:**

-   [Runes and grapheme
    clusters](https://dart.dev/guides/language/language-tour#runes-and-grapheme-clusters)
    in [A tour of the Dart
    language](https://dart.dev/guides/language/language-tour).

Inheritance

:   -   [Object](object-class)
    -   [Iterable](iterable-class)\<[int](int-class)\>
    -   Runes

Available Extensions

:   -   [EnumByName](enumbyname)

Constructors
------------

[Runes](runes/runes)([String](string-class) string)
:   Creates a [Runes](runes-class) iterator for [string](runes/string).

Properties {#instance-properties}
----------

[first](iterable/first) → [int](int-class)

::: {.features}
read-only, inherited
:::

Returns the first element.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](iterable/isempty) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](iterable/isnotempty) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](runes/iterator) → [RuneIterator](runeiterator-class)

::: {.features}
read-only, override
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](runes/last) → [int](int-class)

::: {.features}
read-only, override
:::

Returns the last element.

[length](iterable/length) → [int](int-class)

::: {.features}
read-only, inherited
:::

Returns the number of elements in [this](runes-class).

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](iterable/single) → [int](int-class)

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

[string](runes/string) → [String](string-class)

::: {.features}
final
:::

The string that this is the runes of.

Methods {#instance-methods}
-------

[any](iterable/any)([bool](bool-class) test([int](int-class) element)) →
[bool](bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](iterable/cast)\<R\>() → [Iterable](iterable-class)\<R\>

::: {.features}
inherited
:::

Provides a view of this iterable as an iterable of `R` instances.

[contains](iterable/contains)([Object](object-class)? element) →
[bool](bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](iterable/elementat)([int](int-class) index) →
[int](int-class)

::: {.features}
inherited
:::

Returns the `index`th element.

[every](iterable/every)([bool](bool-class) test([int](int-class)
element)) → [bool](bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](iterable/expand)\<T\>([Iterable](iterable-class)\<T\>
toElements([int](int-class) element)) → [Iterable](iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](iterable-class) into zero or
more elements.

[firstWhere](iterable/firstwhere)([bool](bool-class)
test([int](int-class) element), {[int](int-class) orElse()?}) →
[int](int-class)

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](iterable/fold)\<T\>(T initialValue, T combine(T previousValue,
[int](int-class) element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](iterable/followedby)([Iterable](iterable-class)\<[int](int-class)\>
other) → [Iterable](iterable-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](iterable/foreach)(void action([int](int-class) element)) →
void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[join](iterable/join)(\[[String](string-class) separator = \"\"\]) →
[String](string-class)

::: {.features}
inherited
:::

Converts each element to a [String](string-class) and concatenates the
strings.

[lastWhere](iterable/lastwhere)([bool](bool-class) test([int](int-class)
element), {[int](int-class) orElse()?}) → [int](int-class)

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](iterable/map)\<T\>(T toElement([int](int-class) e)) →
[Iterable](iterable-class)\<T\>

::: {.features}
inherited
:::

The current elements of this iterable modified by `toElement`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](iterable/reduce)([int](int-class) combine([int](int-class)
value, [int](int-class) element)) → [int](int-class)

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[singleWhere](iterable/singlewhere)([bool](bool-class)
test([int](int-class) element), {[int](int-class) orElse()?}) →
[int](int-class)

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](iterable/skip)([int](int-class) count) →
[Iterable](iterable-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Returns an [Iterable](iterable-class) that provides all but the first
`count` elements.

[skipWhile](iterable/skipwhile)([bool](bool-class) test([int](int-class)
value)) → [Iterable](iterable-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](iterable/take)([int](int-class) count) →
[Iterable](iterable-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](iterable/takewhile)([bool](bool-class) test([int](int-class)
value)) → [Iterable](iterable-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](iterable/tolist)({[bool](bool-class) growable = true}) →
[List](list-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Creates a [List](list-class) containing the elements of this
[Iterable](iterable-class).

[toSet](iterable/toset)() → [Set](set-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Creates a [Set](set-class) containing the same elements as this
iterable.

[toString](iterable/tostring)() → [String](string-class)

::: {.features}
inherited
:::

Returns a string representation of (some of) the elements of `this`.

[where](iterable/where)([bool](bool-class) test([int](int-class)
element)) → [Iterable](iterable-class)\<[int](int-class)\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](iterable-class) with all elements that
satisfy the predicate `test`.

[whereType](iterable/wheretype)\<T\>() → [Iterable](iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](iterable-class) with all elements that
have type `T`.

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
<https://api.dart.dev/stable/2.18.5/dart-core/Runes-class.html>
:::
