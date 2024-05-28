[dart:html](../dart-html/dart-html-library){._links-link}

ImmutableListMixin\<E\> class
=============================

Implemented types

:   -   [List](../dart-core/list-class)\<E\>

Implementers

:   -   [DomRectList](domrectlist-class)
    -   [DomStringList](domstringlist-class)
    -   [FileList](filelist-class)
    -   [HtmlCollection](htmlcollection-class)
    -   [LengthList](../dart-svg/lengthlist-class)
    -   [MimeTypeArray](mimetypearray-class)
    -   [NodeList](nodelist-class)
    -   [NumberList](../dart-svg/numberlist-class)
    -   [PluginArray](pluginarray-class)
    -   [SourceBufferList](sourcebufferlist-class)
    -   [SpeechGrammarList](speechgrammarlist-class)
    -   [StringList](../dart-svg/stringlist-class)
    -   [TextTrackCueList](texttrackcuelist-class)
    -   [TextTrackList](texttracklist-class)
    -   [TouchList](touchlist-class)
    -   [TransformList](../dart-svg/transformlist-class)

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[ImmutableListMixin](immutablelistmixin/immutablelistmixin)()

Properties {#instance-properties}
----------

[first](../dart-core/iterable/first) ↔ E

::: {.features}
read / write, inherited
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](../dart-core/iterable/isempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](../dart-core/iterable/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](immutablelistmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, override
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](../dart-core/iterable/last) ↔ E

::: {.features}
read / write, inherited
:::

Returns the last element.

[length](../dart-core/list/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, inherited
:::

The number of objects in this list.

[reversed](../dart-core/list/reversed) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
read-only, inherited
:::

An [Iterable](../dart-core/iterable-class) of the objects in this list
in reverse order.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](../dart-core/iterable/single) → E

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](immutablelistmixin/add)(E value) → void

::: {.features}
override
:::

Adds `value` to the end of this list, extending the length by one.

[addAll](immutablelistmixin/addall)([Iterable](../dart-core/iterable-class)\<E\>
iterable) → void

::: {.features}
override
:::

Appends all objects of `iterable` to the end of this list.

[any](../dart-core/iterable/any)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](../dart-core/list/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class), E\>

::: {.features}
inherited
:::

An unmodifiable [Map](../dart-core/map-class) view of this list.

[cast](../dart-core/list/cast)\<R\>() →
[List](../dart-core/list-class)\<R\>

::: {.features}
inherited
:::

Returns a view of this list as a list of `R` instances.

[clear](../dart-core/list/clear)() → void

::: {.features}
inherited
:::

Removes all objects from this list; the length of the list becomes zero.

[contains](../dart-core/iterable/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](../dart-core/iterable/elementat)([int](../dart-core/int-class)
index) → E

::: {.features}
inherited
:::

Returns the `index`th element.

[every](../dart-core/iterable/every)([bool](../dart-core/bool-class)
test(E element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-core/iterable/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
toElements(E element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](immutablelistmixin/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end, \[E? fillValue\]) → void

::: {.features}
override
:::

Overwrites a range of elements with `fillValue`.

[firstWhere](../dart-core/iterable/firstwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-core/iterable/fold)\<T\>(T initialValue, T combine(T
previousValue, E element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-core/iterable/followedby)([Iterable](../dart-core/iterable-class)\<E\>
other) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-core/iterable/foreach)(void action(E element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](../dart-core/list/getrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Creates an [Iterable](../dart-core/iterable-class) that iterates over a
range of elements.

[indexOf](../dart-core/list/indexof)(E element,
\[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index of `element` in this list.

[indexWhere](../dart-core/list/indexwhere)([bool](../dart-core/bool-class)
test(E element), \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[insert](immutablelistmixin/insert)([int](../dart-core/int-class) index,
E element) → void

::: {.features}
override
:::

Inserts `element` at position `index` in this list.

[insertAll](immutablelistmixin/insertall)([int](../dart-core/int-class)
index, [Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
override
:::

Inserts all objects of `iterable` at position `index` in this list.

[join](../dart-core/iterable/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastIndexOf](../dart-core/list/lastindexof)(E element,
\[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index of `element` in this list.

[lastIndexWhere](../dart-core/list/lastindexwhere)([bool](../dart-core/bool-class)
test(E element), \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](../dart-core/iterable/lastwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](../dart-core/iterable/map)\<T\>(T toElement(E e)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

The current elements of this iterable modified by `toElement`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](../dart-core/iterable/reduce)(E combine(E value, E element)) →
E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](immutablelistmixin/remove)([Object](../dart-core/object-class)?
object) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Removes the first occurrence of `value` from this list.

[removeAt](immutablelistmixin/removeat)([int](../dart-core/int-class)
pos) → E

::: {.features}
override
:::

Removes the object at position `index` from this list.

[removeLast](immutablelistmixin/removelast)() → E

::: {.features}
override
:::

Removes and returns the last object in this list.

[removeRange](immutablelistmixin/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
override
:::

Removes a range of elements from the list.

[removeWhere](immutablelistmixin/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
override
:::

Removes all objects from this list that satisfy `test`.

[replaceRange](immutablelistmixin/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
override
:::

Replaces a range of elements with the elements of `replacements`.

[retainWhere](immutablelistmixin/retainwhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
override
:::

Removes all objects from this list that fail to satisfy `test`.

[setAll](immutablelistmixin/setall)([int](../dart-core/int-class) index,
[Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
override
:::

Overwrites elements with the objects of `iterable`.

[setRange](immutablelistmixin/setrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> iterable,
\[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
override
:::

Writes some elements of `iterable` into a range of this list.

[shuffle](immutablelistmixin/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
override
:::

Shuffles the elements of this list randomly.

[singleWhere](../dart-core/iterable/singlewhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-core/iterable/skip)([int](../dart-core/int-class) count)
→ [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-core/iterable/skipwhile)([bool](../dart-core/bool-class)
test(E value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](immutablelistmixin/sort)(\[[int](../dart-core/int-class)
compare(E a, E b)?\]) → void

::: {.features}
override
:::

Sorts this list according to the order specified by the `compare`
function.

[sublist](../dart-core/list/sublist)([int](../dart-core/int-class)
start, \[[int](../dart-core/int-class)? end\]) →
[List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Returns a new list containing the elements between `start` and `end`.

[take](../dart-core/iterable/take)([int](../dart-core/int-class) count)
→ [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-core/iterable/takewhile)([bool](../dart-core/bool-class)
test(E value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-core/iterable/tolist)({[bool](../dart-core/bool-class)
growable = true}) → [List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-core/iterable/toset)() →
[Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[where](../dart-core/iterable/where)([bool](../dart-core/bool-class)
test(E element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](../dart-core/iterable/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

Operators
---------

[operator
+](../dart-core/list/operator_plus)([List](../dart-core/list-class)\<E\>
other) → [List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Returns the concatenation of this list and `other`.

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](../dart-core/list/operator_get)([int](../dart-core/int-class)
index) → E

::: {.features}
inherited
:::

The object at the given `index` in the list.

[operator
\[\]=](../dart-core/list/operator_put)([int](../dart-core/int-class)
index, E value) → void

::: {.features}
inherited
:::

Sets the value at the given `index` in the list to `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImmutableListMixin-class.html>
:::
