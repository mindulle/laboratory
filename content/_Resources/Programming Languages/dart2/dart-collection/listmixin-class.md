[dart:collection](../dart-collection/dart-collection-library){._links-link}

ListMixin\<E\> class
====================

Base implementation of a [List](../dart-core/list-class) class.

`ListMixin` can be used as a mixin to make a class implement the `List`
interface.

This mixin implements all read operations using only the `length` and
`operator[]` and members. It implements write operations using those and
`add`, `length=` and `operator[]=`. Classes using this mixin should
implement those five operations.

**NOTICE**: For backwards compatibility reasons, there is a default
implementation of `add` which only works for lists with a nullable
element type. For lists with a non-nullable element type, the `add`
method must be implemented.

**NOTICE**: Forwarding just the four `length` and `[]` read/write
operations to a normal growable [List](../dart-core/list-class) (as
created by a `[]` literal) will give very bad performance for `add` and
`addAll` operations of `ListMixin`. These operations are implemented by
increasing the length of the list by one for each `add` operation, and
repeatedly increasing the length of a growable list is not efficient. To
avoid this, override \'add\' and \'addAll\' to also forward directly to
the growable list, or, if possible, use `DelegatingList` from
\"package:collection/collection.dart\" instead of a `ListMixin`.

Implemented types

:   -   [List](../dart-core/list-class)\<E\>

Implementers

:   -   [DomRectList](../dart-html/domrectlist-class)
    -   [DomStringList](../dart-html/domstringlist-class)
    -   [FileList](../dart-html/filelist-class)
    -   [HtmlCollection](../dart-html/htmlcollection-class)
    -   [JsArray](../dart-js/jsarray-class)
    -   [LengthList](../dart-svg/lengthlist-class)
    -   [ListBase](listbase-class)
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

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[ListMixin](listmixin/listmixin)()

Properties {#instance-properties}
----------

[first](listmixin/first) ↔ E

::: {.features}
read / write, override
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](listmixin/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this collection has no elements.

[isNotEmpty](listmixin/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this collection has at least one element.

[iterator](listmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, override
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](listmixin/last) ↔ E

::: {.features}
read / write, override
:::

Returns the last element.

[length](../dart-core/list/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, inherited
:::

The number of objects in this list.

[reversed](listmixin/reversed) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
read-only, override
:::

An [Iterable](../dart-core/iterable-class) of the objects in this list
in reverse order.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](listmixin/single) → E

::: {.features}
read-only, override
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](listmixin/add)(E element) → void

::: {.features}
override
:::

Adds `value` to the end of this list, extending the length by one.

[addAll](listmixin/addall)([Iterable](../dart-core/iterable-class)\<E\>
iterable) → void

::: {.features}
override
:::

Appends all objects of `iterable` to the end of this list.

[any](listmixin/any)([bool](../dart-core/bool-class) test(E element)) →
[bool](../dart-core/bool-class)

::: {.features}
override
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](listmixin/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class), E\>

::: {.features}
override
:::

An unmodifiable [Map](../dart-core/map-class) view of this list.

[cast](listmixin/cast)\<R\>() → [List](../dart-core/list-class)\<R\>

::: {.features}
override
:::

Returns a view of this list as a list of `R` instances.

[clear](listmixin/clear)() → void

::: {.features}
override
:::

Removes all objects from this list; the length of the list becomes zero.

[contains](listmixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether the collection contains an element equal to `element`.

[elementAt](listmixin/elementat)([int](../dart-core/int-class) index) →
E

::: {.features}
override
:::

Returns the `index`th element.

[every](listmixin/every)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Checks whether every element of this iterable satisfies `test`.

[expand](listmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f(E element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
override
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](listmixin/fillrange)([int](../dart-core/int-class) start,
[int](../dart-core/int-class) end, \[E? fill\]) → void

::: {.features}
override
:::

Overwrites a range of elements with `fillValue`.

[firstWhere](listmixin/firstwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
override
:::

Returns the first element that satisfies the given predicate `test`.

[fold](listmixin/fold)\<T\>(T initialValue, T combine(T previousValue, E
element)) → T

::: {.features}
override
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](listmixin/followedby)([Iterable](../dart-core/iterable-class)\<E\>
other) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](listmixin/foreach)(void action(E element)) → void

::: {.features}
override
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](listmixin/getrange)([int](../dart-core/int-class) start,
[int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Creates an [Iterable](../dart-core/iterable-class) that iterates over a
range of elements.

[indexOf](listmixin/indexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

The first index of `element` in this list.

[indexWhere](listmixin/indexwhere)([bool](../dart-core/bool-class)
test(E element), \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

The first index in the list that satisfies the provided `test`.

[insert](listmixin/insert)([int](../dart-core/int-class) index, E
element) → void

::: {.features}
override
:::

Inserts `element` at position `index` in this list.

[insertAll](listmixin/insertall)([int](../dart-core/int-class) index,
[Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
override
:::

Inserts all objects of `iterable` at position `index` in this list.

[join](listmixin/join)(\[[String](../dart-core/string-class) separator =
\"\"\]) → [String](../dart-core/string-class)

::: {.features}
override
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastIndexOf](listmixin/lastindexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

The last index of `element` in this list.

[lastIndexWhere](listmixin/lastindexwhere)([bool](../dart-core/bool-class)
test(E element), \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
override
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](listmixin/lastwhere)([bool](../dart-core/bool-class) test(E
element), {E orElse()?}) → E

::: {.features}
override
:::

Returns the last element that satisfies the given predicate `test`.

[map](listmixin/map)\<T\>(T f(E element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
override
:::

The current elements of this iterable modified by `toElement`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](listmixin/reduce)(E combine(E previousValue, E element)) → E

::: {.features}
override
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](listmixin/remove)([Object](../dart-core/object-class)? element)
→ [bool](../dart-core/bool-class)

::: {.features}
override
:::

Removes the first occurrence of `value` from this list.

[removeAt](listmixin/removeat)([int](../dart-core/int-class) index) → E

::: {.features}
override
:::

Removes the object at position `index` from this list.

[removeLast](listmixin/removelast)() → E

::: {.features}
override
:::

Removes and returns the last object in this list.

[removeRange](listmixin/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
override
:::

Removes a range of elements from the list.

[removeWhere](listmixin/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
override
:::

Removes all objects from this list that satisfy `test`.

[replaceRange](listmixin/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> newContents) → void

::: {.features}
override
:::

Replaces a range of elements with the elements of `replacements`.

[retainWhere](listmixin/retainwhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
override
:::

Removes all objects from this list that fail to satisfy `test`.

[setAll](listmixin/setall)([int](../dart-core/int-class) index,
[Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
override
:::

Overwrites elements with the objects of `iterable`.

[setRange](listmixin/setrange)([int](../dart-core/int-class) start,
[int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> iterable,
\[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
override
:::

Writes some elements of `iterable` into a range of this list.

[shuffle](listmixin/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
override
:::

Shuffles the elements of this list randomly.

[singleWhere](listmixin/singlewhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
override
:::

Returns the single element that satisfies `test`.

[skip](listmixin/skip)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](listmixin/skipwhile)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](listmixin/sort)(\[[int](../dart-core/int-class) compare(E a, E
b)?\]) → void

::: {.features}
override
:::

Sorts this list according to the order specified by the `compare`
function.

[sublist](listmixin/sublist)([int](../dart-core/int-class) start,
\[[int](../dart-core/int-class)? end\]) →
[List](../dart-core/list-class)\<E\>

::: {.features}
override
:::

Returns a new list containing the elements between `start` and `end`.

[take](listmixin/take)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](listmixin/takewhile)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](listmixin/tolist)({[bool](../dart-core/bool-class) growable =
true}) → [List](../dart-core/list-class)\<E\>

::: {.features}
override
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](listmixin/toset)() → [Set](../dart-core/set-class)\<E\>

::: {.features}
override
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](listmixin/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

[where](listmixin/where)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](listmixin/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
override
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

Operators
---------

[operator
+](listmixin/operator_plus)([List](../dart-core/list-class)\<E\> other)
→ [List](../dart-core/list-class)\<E\>

::: {.features}
override
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
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin-class.html>
:::
