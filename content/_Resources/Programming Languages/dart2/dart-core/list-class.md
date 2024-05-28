[dart:core](../dart-core/dart-core-library){._links-link}

List\<E\> class
===============

An indexable collection of objects with a length.

Subclasses of this class implement different kinds of lists. The most
common kinds of lists are:

-   **Fixed-length list**

    An error occurs when attempting to use operations that can change
    the length of the list.

-   **Growable list**

    Full implementation of the API defined in this class.

The default growable list, as created by `[]`, keeps an internal buffer,
and grows that buffer when necessary. This guarantees that a sequence of
[add](list/add) operations will each execute in amortized constant time.
Setting the length directly may take time proportional to the new
length, and may change the internal capacity so that a following add
operation will need to immediately increase the buffer capacity. Other
list implementations may have different performance behavior.

Example of fixed-length list:

``` {.language-dart data-language="dart"}
final fixedLengthList = List<int>.filled(5, 0); // Creates fixed-length list.
print(fixedLengthList); // [0, 0, 0, 0, 0]
fixedLengthList[0] = 87;
fixedLengthList.setAll(1, [1, 2, 3]);
print(fixedLengthList); // [87, 1, 2, 3, 0]
// Fixed length list length can't be changed or increased
fixedLengthList.length = 0;  // Throws
fixedLengthList.add(499);    // Throws
```

Example of growable list:

``` {.language-dart data-language="dart"}
final growableList = <String>['A', 'B']; // Creates growable list.
```

To add data to the growable list, use
[operator\[\]=](list/operator_put), [add](list/add) or
[addAll](list/addall).

``` {.language-dart data-language="dart"}
growableList[0] = 'G';
print(growableList); // [G, B]
growableList.add('X');
growableList.addAll({'C', 'B'});
print(growableList); // [G, B, X, C, B]
```

To check whether, and where, the element is in the list, use
[indexOf](list/indexof) or [lastIndexOf](list/lastindexof).

``` {.language-dart data-language="dart"}
final indexA = growableList.indexOf('A'); // -1 (not in the list)
final firstIndexB = growableList.indexOf('B'); // 1
final lastIndexB = growableList.lastIndexOf('B'); // 4
```

To remove an element from the growable list, use [remove](list/remove),
[removeAt](list/removeat), [removeLast](list/removelast),
[removeRange](list/removerange) or [removeWhere](list/removewhere).

``` {.language-dart data-language="dart"}
growableList.remove('C');
growableList.removeLast();
print(growableList); // [G, B, X]
```

To insert an element at position in the list, use [insert](list/insert)
or [insertAll](list/insertall).

``` {.language-dart data-language="dart"}
growableList.insert(1, 'New');
print(growableList); // [G, New, B, X]
```

To replace a range of elements in the list, use
[fillRange](list/fillrange), [replaceRange](list/replacerange) or
[setRange](list/setrange).

``` {.language-dart data-language="dart"}
growableList.replaceRange(0, 2, ['AB', 'A']);
print(growableList); // [AB, A, B, X]
growableList.fillRange(2, 4, 'F');
print(growableList); // [AB, A, F, F]
```

To sort the elements of the list, use [sort](list/sort).

``` {.language-dart data-language="dart"}
growableList.sort((a, b) => a.compareTo(b));
print(growableList); // [A, AB, F, F]
```

To shuffle the elements of this list randomly, use
[shuffle](list/shuffle).

``` {.language-dart data-language="dart"}
growableList.shuffle();
print(growableList); // e.g. [AB, F, A, F]
```

To find the first element satisfying some predicate, or give a default
value if none do, use [firstWhere](iterable/firstwhere).

``` {.language-dart data-language="dart"}
bool isVowel(String char) => char.length == 1 && "AEIOU".contains(char);
final firstVowel = growableList.firstWhere(isVowel, orElse: () => ''); // ''
```

There are similar [lastWhere](iterable/lastwhere) and
[singleWhere](iterable/singlewhere) methods.

A list is an [Iterable](iterable-class) and supports all its methods,
including [where](iterable/where), [map](iterable/map),
[whereType](iterable/wheretype) and [toList](iterable/tolist).

Lists are [Iterable](iterable-class). Iteration occurs over values in
index order. Changing the values does not affect iteration, but changing
the valid indices---that is, changing the list\'s length---between
iteration steps causes a
[ConcurrentModificationError](concurrentmodificationerror-class). This
means that only growable lists can throw ConcurrentModificationError. If
the length changes temporarily and is restored before continuing the
iteration, the iterator might not detect it.

It is generally not allowed to modify the list\'s length (adding or
removing elements) while an operation on the list is being performed,
for example during a call to [forEach](iterable/foreach) or
[sort](list/sort). Changing the list\'s length while it is being
iterated, either by iterating it directly or through iterating an
[Iterable](iterable-class) that is backed by the list, will break the
iteration.

Implemented types

:   -   [Iterable](iterable-class)\<T\>

Implementers

:   -   [DomRectList](../dart-html/domrectlist-class)
    -   [DomStringList](../dart-html/domstringlist-class)
    -   [FileList](../dart-html/filelist-class)
    -   [Float32List](../dart-typed_data/float32list-class)
    -   [Float32x4List](../dart-typed_data/float32x4list-class)
    -   [Float64List](../dart-typed_data/float64list-class)
    -   [Float64x2List](../dart-typed_data/float64x2list-class)
    -   [HtmlCollection](../dart-html/htmlcollection-class)
    -   [ImmutableListMixin](../dart-html/immutablelistmixin-class)
    -   [Int8List](../dart-typed_data/int8list-class)
    -   [Int16List](../dart-typed_data/int16list-class)
    -   [Int32List](../dart-typed_data/int32list-class)
    -   [Int32x4List](../dart-typed_data/int32x4list-class)
    -   [Int64List](../dart-typed_data/int64list-class)
    -   [LengthList](../dart-svg/lengthlist-class)
    -   [ListMixin](../dart-collection/listmixin-class)
    -   [MimeTypeArray](../dart-html/mimetypearray-class)
    -   [NodeList](../dart-html/nodelist-class)
    -   [NumberList](../dart-svg/numberlist-class)
    -   [PluginArray](../dart-html/pluginarray-class)
    -   [SourceBufferList](../dart-html/sourcebufferlist-class)
    -   [SpeechGrammarList](../dart-html/speechgrammarlist-class)
    -   [StringList](../dart-svg/stringlist-class)
    -   [TextTrackCueList](../dart-html/texttrackcuelist-class)
    -   [TextTrackList](../dart-html/texttracklist-class)
    -   [TouchList](../dart-html/touchlist-class)
    -   [TransformList](../dart-svg/transformlist-class)
    -   [Uint8ClampedList](../dart-typed_data/uint8clampedlist-class)
    -   [Uint8List](../dart-typed_data/uint8list-class)
    -   [Uint16List](../dart-typed_data/uint16list-class)
    -   [Uint32List](../dart-typed_data/uint32list-class)
    -   [Uint64List](../dart-typed_data/uint64list-class)
    -   [UnmodifiableFloat32ListView](../dart-typed_data/unmodifiablefloat32listview-class)
    -   [UnmodifiableFloat32x4ListView](../dart-typed_data/unmodifiablefloat32x4listview-class)
    -   [UnmodifiableFloat64ListView](../dart-typed_data/unmodifiablefloat64listview-class)
    -   [UnmodifiableFloat64x2ListView](../dart-typed_data/unmodifiablefloat64x2listview-class)
    -   [UnmodifiableInt8ListView](../dart-typed_data/unmodifiableint8listview-class)
    -   [UnmodifiableInt16ListView](../dart-typed_data/unmodifiableint16listview-class)
    -   [UnmodifiableInt32ListView](../dart-typed_data/unmodifiableint32listview-class)
    -   [UnmodifiableInt32x4ListView](../dart-typed_data/unmodifiableint32x4listview-class)
    -   [UnmodifiableInt64ListView](../dart-typed_data/unmodifiableint64listview-class)
    -   [UnmodifiableListView](../dart-collection/unmodifiablelistview-class)
    -   [UnmodifiableUint8ClampedListView](../dart-typed_data/unmodifiableuint8clampedlistview-class)
    -   [UnmodifiableUint8ListView](../dart-typed_data/unmodifiableuint8listview-class)
    -   [UnmodifiableUint16ListView](../dart-typed_data/unmodifiableuint16listview-class)
    -   [UnmodifiableUint32ListView](../dart-typed_data/unmodifiableuint32listview-class)
    -   [UnmodifiableUint64ListView](../dart-typed_data/unmodifiableuint64listview-class)

Available Extensions

:   -   [EnumByName](enumbyname)

Constructors
------------

[List](list/list){.deprecated}(\[[int](int-class)? length\])

::: {.constructor-modifier .features}
factory
:::

Creates a list of the given length.

[List.empty](list/list.empty)({[bool](bool-class) growable = false})

::: {.constructor-modifier .features}
factory
:::

Creates a new empty list.

[List.filled](list/list.filled)([int](int-class) length, E fill,
{[bool](bool-class) growable = false})

::: {.constructor-modifier .features}
factory
:::

Creates a list of the given length with `fill` at each position.

[List.from](list/list.from)([Iterable](iterable-class) elements,
{[bool](bool-class) growable = true})

::: {.constructor-modifier .features}
factory
:::

Creates a list containing all `elements`.

[List.generate](list/list.generate)([int](int-class) length, E
generator([int](int-class) index), {[bool](bool-class) growable = true})

::: {.constructor-modifier .features}
factory
:::

Generates a list of values.

[List.of](list/list.of)([Iterable](iterable-class)\<E\> elements,
{[bool](bool-class) growable = true})

::: {.constructor-modifier .features}
factory
:::

Creates a list from `elements`.

[List.unmodifiable](list/list.unmodifiable)([Iterable](iterable-class)
elements)

::: {.constructor-modifier .features}
factory
:::

Creates an unmodifiable list containing all `elements`.

Properties {#instance-properties}
----------

[first](list/first) ↔ E

::: {.features}
read / write, inherited-getter
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

[iterator](iterable/iterator) → [Iterator](iterator-class)\<E\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](list/last) ↔ E

::: {.features}
read / write, inherited-getter
:::

Returns the last element.

[length](list/length) ↔ [int](int-class)

::: {.features}
read / write
:::

The number of objects in this list.

[reversed](list/reversed) → [Iterable](iterable-class)\<E\>

::: {.features}
read-only
:::

An [Iterable](iterable-class) of the objects in this list in reverse
order.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](iterable/single) → E

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](list/add)(E value) → void

Adds `value` to the end of this list, extending the length by one.

[addAll](list/addall)([Iterable](iterable-class)\<E\> iterable) → void

Appends all objects of `iterable` to the end of this list.

[any](iterable/any)([bool](bool-class) test(E element)) →
[bool](bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](list/asmap)() → [Map](map-class)\<[int](int-class), E\>

An unmodifiable [Map](map-class) view of this list.

[cast](list/cast)\<R\>() → [List](list-class)\<R\>

::: {.features}
override
:::

Returns a view of this list as a list of `R` instances.

[clear](list/clear)() → void

Removes all objects from this list; the length of the list becomes zero.

[contains](iterable/contains)([Object](object-class)? element) →
[bool](bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](iterable/elementat)([int](int-class) index) → E

::: {.features}
inherited
:::

Returns the `index`th element.

[every](iterable/every)([bool](bool-class) test(E element)) →
[bool](bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](iterable/expand)\<T\>([Iterable](iterable-class)\<T\>
toElements(E element)) → [Iterable](iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](iterable-class) into zero or
more elements.

[fillRange](list/fillrange)([int](int-class) start, [int](int-class)
end, \[E? fillValue\]) → void

Overwrites a range of elements with `fillValue`.

[firstWhere](iterable/firstwhere)([bool](bool-class) test(E element), {E
orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](iterable/fold)\<T\>(T initialValue, T combine(T previousValue, E
element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](iterable/followedby)([Iterable](iterable-class)\<E\> other)
→ [Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](iterable/foreach)(void action(E element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](list/getrange)([int](int-class) start, [int](int-class) end)
→ [Iterable](iterable-class)\<E\>

Creates an [Iterable](iterable-class) that iterates over a range of
elements.

[indexOf](list/indexof)(E element, \[[int](int-class) start = 0\]) →
[int](int-class)

The first index of `element` in this list.

[indexWhere](list/indexwhere)([bool](bool-class) test(E element),
\[[int](int-class) start = 0\]) → [int](int-class)

The first index in the list that satisfies the provided `test`.

[insert](list/insert)([int](int-class) index, E element) → void

Inserts `element` at position `index` in this list.

[insertAll](list/insertall)([int](int-class) index,
[Iterable](iterable-class)\<E\> iterable) → void

Inserts all objects of `iterable` at position `index` in this list.

[join](iterable/join)(\[[String](string-class) separator = \"\"\]) →
[String](string-class)

::: {.features}
inherited
:::

Converts each element to a [String](string-class) and concatenates the
strings.

[lastIndexOf](list/lastindexof)(E element, \[[int](int-class)? start\])
→ [int](int-class)

The last index of `element` in this list.

[lastIndexWhere](list/lastindexwhere)([bool](bool-class) test(E
element), \[[int](int-class)? start\]) → [int](int-class)

The last index in the list that satisfies the provided `test`.

[lastWhere](iterable/lastwhere)([bool](bool-class) test(E element), {E
orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](iterable/map)\<T\>(T toElement(E e)) →
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

[reduce](iterable/reduce)(E combine(E value, E element)) → E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](list/remove)([Object](object-class)? value) →
[bool](bool-class)

Removes the first occurrence of `value` from this list.

[removeAt](list/removeat)([int](int-class) index) → E

Removes the object at position `index` from this list.

[removeLast](list/removelast)() → E

Removes and returns the last object in this list.

[removeRange](list/removerange)([int](int-class) start, [int](int-class)
end) → void

Removes a range of elements from the list.

[removeWhere](list/removewhere)([bool](bool-class) test(E element)) →
void

Removes all objects from this list that satisfy `test`.

[replaceRange](list/replacerange)([int](int-class) start,
[int](int-class) end, [Iterable](iterable-class)\<E\> replacements) →
void

Replaces a range of elements with the elements of `replacements`.

[retainWhere](list/retainwhere)([bool](bool-class) test(E element)) →
void

Removes all objects from this list that fail to satisfy `test`.

[setAll](list/setall)([int](int-class) index,
[Iterable](iterable-class)\<E\> iterable) → void

Overwrites elements with the objects of `iterable`.

[setRange](list/setrange)([int](int-class) start, [int](int-class) end,
[Iterable](iterable-class)\<E\> iterable, \[[int](int-class) skipCount =
0\]) → void

Writes some elements of `iterable` into a range of this list.

[shuffle](list/shuffle)(\[[Random](../dart-math/random-class)? random\])
→ void

Shuffles the elements of this list randomly.

[singleWhere](iterable/singlewhere)([bool](bool-class) test(E element),
{E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](iterable/skip)([int](int-class) count) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](iterable-class) that provides all but the first
`count` elements.

[skipWhile](iterable/skipwhile)([bool](bool-class) test(E value)) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](list/sort)(\[[int](int-class) compare(E a, E b)?\]) → void

Sorts this list according to the order specified by the `compare`
function.

[sublist](list/sublist)([int](int-class) start, \[[int](int-class)?
end\]) → [List](list-class)\<E\>

Returns a new list containing the elements between `start` and `end`.

[take](iterable/take)([int](int-class) count) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](iterable/takewhile)([bool](bool-class) test(E value)) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](iterable/tolist)({[bool](bool-class) growable = true}) →
[List](list-class)\<E\>

::: {.features}
inherited
:::

Creates a [List](list-class) containing the elements of this
[Iterable](iterable-class).

[toSet](iterable/toset)() → [Set](set-class)\<E\>

::: {.features}
inherited
:::

Creates a [Set](set-class) containing the same elements as this
iterable.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

[where](iterable/where)([bool](bool-class) test(E element)) →
[Iterable](iterable-class)\<E\>

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

[operator +](list/operator_plus)([List](list-class)\<E\> other) →
[List](list-class)\<E\>

Returns the concatenation of this list and `other`.

[operator ==](list/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Whether this list is equal to `other`.

[operator \[\]](list/operator_get)([int](int-class) index) → E

The object at the given `index` in the list.

[operator \[\]=](list/operator_put)([int](int-class) index, E value) →
void

Sets the value at the given `index` in the list to `value`.

Static Methods
--------------

[castFrom](list/castfrom)\<S, T\>([List](list-class)\<S\> source) →
[List](list-class)\<T\>

::: {.features}
override
:::

Adapts `source` to be a `List<T>`.

[copyRange](list/copyrange)\<T\>([List](list-class)\<T\> target,
[int](int-class) at, [List](list-class)\<T\> source, \[[int](int-class)?
start, [int](int-class)? end\]) → void

Copy a range of one list into another list.

[writeIterable](list/writeiterable)\<T\>([List](list-class)\<T\> target,
[int](int-class) at, [Iterable](iterable-class)\<T\> source) → void

Write the elements of an iterable into a list.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List-class.html>
:::
