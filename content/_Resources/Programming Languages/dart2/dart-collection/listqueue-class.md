[dart:collection](../dart-collection/dart-collection-library){._links-link}

ListQueue\<E\> class
====================

List based [Queue](queue-class).

Keeps a cyclic buffer of elements, and grows to a larger buffer when it
fills up. This guarantees constant time peek and remove operations, and
amortized constant time add operations.

The structure is efficient for any queue or stack usage.

Example:

``` {.language-dart data-language="dart"}
final queue = ListQueue<int>();
```

To add objects to a queue, use [add](listqueue/add),
[addAll](listqueue/addall), [addFirst](listqueue/addfirst)
or[addLast](listqueue/addlast).

``` {.language-dart data-language="dart"}
queue.add(5);
queue.addFirst(0);
queue.addLast(10);
queue.addAll([1, 2, 3]);
print(queue); // {0, 5, 10, 1, 2, 3}
```

To check if the queue is empty, use [isEmpty](listqueue/isempty) or
[isNotEmpty](../dart-core/iterable/isnotempty). To find the number of
queue entries, use [length](listqueue/length).

``` {.language-dart data-language="dart"}
final isEmpty = queue.isEmpty; // false
final queueSize = queue.length; // 6
```

To get first or last item from queue, use [first](listqueue/first) or
[last](listqueue/last).

``` {.language-dart data-language="dart"}
final first = queue.first; // 0
final last = queue.last; // 3
```

To get item value using index, use [elementAt](listqueue/elementat).

``` {.language-dart data-language="dart"}
final itemAt = queue.elementAt(2); // 10
```

To convert queue to list, call [toList](listqueue/tolist).

``` {.language-dart data-language="dart"}
final numbers = queue.toList();
print(numbers); // [0, 5, 10, 1, 2, 3]
```

To remove item from queue, call [remove](listqueue/remove),
[removeFirst](listqueue/removefirst) or
[removeLast](listqueue/removelast).

``` {.language-dart data-language="dart"}
queue.remove(10);
queue.removeFirst();
queue.removeLast();
print(queue); // {5, 1, 2}
```

To remove multiple elements at the same time, use
[removeWhere](listqueue/removewhere).

``` {.language-dart data-language="dart"}
queue.removeWhere((element) => element == 1);
print(queue); // {5, 2}
```

To remove all elements in this queue that do not meet a condition, use
[retainWhere](listqueue/retainwhere).

``` {.language-dart data-language="dart"}
queue.retainWhere((element) => element < 4);
print(queue); // {2}
```

To remove all items and empty the set, use [clear](listqueue/clear).

``` {.language-dart data-language="dart"}
queue.clear();
print(queue.isEmpty); // true
print(queue); // {}
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Iterable](../dart-core/iterable-class)\<E\>
    -   ListQueue

Implemented types

:   -   [Queue](queue-class)\<E\>

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[ListQueue](listqueue/listqueue)(\[[int](../dart-core/int-class)?
initialCapacity\])

Create an empty queue.

[ListQueue.from](listqueue/listqueue.from)([Iterable](../dart-core/iterable-class)
elements)

::: {.constructor-modifier .features}
factory
:::

Create a `ListQueue` containing all `elements`.

[ListQueue.of](listqueue/listqueue.of)([Iterable](../dart-core/iterable-class)\<E\>
elements)

::: {.constructor-modifier .features}
factory
:::

Create a `ListQueue` from `elements`.

Properties {#instance-properties}
----------

[first](listqueue/first) → E

::: {.features}
read-only
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](listqueue/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether this collection has no elements.

[isNotEmpty](../dart-core/iterable/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](listqueue/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](listqueue/last) → E

::: {.features}
read-only
:::

Returns the last element.

[length](listqueue/length) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Returns the number of elements in the iterable.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](listqueue/single) → E

::: {.features}
read-only
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](listqueue/add)(E value) → void

::: {.features}
override
:::

Adds `value` at the end of the queue.

[addAll](listqueue/addall)([Iterable](../dart-core/iterable-class)\<E\>
elements) → void

::: {.features}
override
:::

Adds all elements of `iterable` at the end of the queue. The length of
the queue is extended by the length of `iterable`.

[addFirst](listqueue/addfirst)(E value) → void

::: {.features}
override
:::

Adds `value` at the beginning of the queue.

[addLast](listqueue/addlast)(E value) → void

::: {.features}
override
:::

Adds `value` at the end of the queue.

[any](listqueue/any)([bool](../dart-core/bool-class) test(E element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](listqueue/cast)\<R\>() → [Queue](queue-class)\<R\>

::: {.features}
override
:::

Provides a view of this iterable as an iterable of `R` instances.

[clear](listqueue/clear)() → void

::: {.features}
override
:::

Removes all elements in the queue. The size of the queue becomes zero.

[contains](listqueue/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](listqueue/elementat)([int](../dart-core/int-class) index) →
E

Returns the `index`th element.

[every](listqueue/every)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

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

[firstWhere](listqueue/firstwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](listqueue/fold)\<T\>(T initialValue, T combine(T previousValue, E
element)) → T

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

[forEach](listqueue/foreach)(void f(E element)) → void

Invokes `action` on each element of this iterable in iteration order.

[join](listqueue/join)(\[[String](../dart-core/string-class) separator =
\"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastWhere](listqueue/lastwhere)([bool](../dart-core/bool-class) test(E
element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](listqueue/map)\<T\>(T toElement(E element)) →
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

[reduce](listqueue/reduce)(E combine(E value, E element)) → E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](listqueue/remove)([Object](../dart-core/object-class)? value) →
[bool](../dart-core/bool-class)

::: {.features}
override
:::

Removes a single instance of `value` from the queue.

[removeFirst](listqueue/removefirst)() → E

::: {.features}
override
:::

Removes and returns the first element of this queue.

[removeLast](listqueue/removelast)() → E

::: {.features}
override
:::

Removes and returns the last element of the queue.

[removeWhere](listqueue/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
override
:::

Remove all elements matched by `test`.

[retainWhere](listqueue/retainwhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
override
:::

Remove all elements not matched by `test`.

[singleWhere](listqueue/singlewhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](listqueue/skip)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](listqueue/skipwhile)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](listqueue/take)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](listqueue/takewhile)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](listqueue/tolist)({[bool](../dart-core/bool-class) growable =
true}) → [List](../dart-core/list-class)\<E\>

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](listqueue/toset)() → [Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](listqueue/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

Returns a string representation of (some of) the elements of `this`.

[where](listqueue/where)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

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
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue-class.html>
:::
