[dart:collection](../dart-collection/dart-collection-library){._links-link}

LinkedList\<E extends LinkedListEntry\<E\>\> class
==================================================

A specialized double-linked list of elements that extends
[LinkedListEntry](linkedlistentry-class).

This is not a generic data structure. It only accepts elements that
*extend* the [LinkedListEntry](linkedlistentry-class) class. See the
[Queue](queue-class) implementations for generic collections that allow
constant time adding and removing at the ends.

This is not a [List](../dart-core/list-class) implementation. Despite
its name, this class does not implement the
[List](../dart-core/list-class) interface. It does not allow constant
time lookup by index.

Because the elements themselves contain the links of this linked list,
each element can be in only one list at a time. To add an element to
another list, it must first be removed from its current list (if any).
For the same reason, the [remove](linkedlist/remove) and
[contains](linkedlist/contains) methods are based on *identity*, even if
the [LinkedListEntry](linkedlistentry-class) chooses to override
[Object.==](../dart-core/object/operator_equals).

In return, each element knows its own place in the linked list, as well
as which list it is in. This allows constant time
[LinkedListEntry.insertAfter](linkedlistentry/insertafter),
[LinkedListEntry.insertBefore](linkedlistentry/insertbefore) and
[LinkedListEntry.unlink](linkedlistentry/unlink) operations when all you
have is the element.

A `LinkedList` also allows constant time adding and removing at either
end, and a constant time length getter.

Example:

``` {.language-dart data-language="dart"}
class EntryItem extends LinkedListEntry<EntryItem> {
  final int id;
  final String text;
  EntryItem(this.id, this.text);

  @override
  String toString() {
    return '$id : $text';
  }
}

void main(){
  final linkedList = LinkedList<EntryItem>();
  linkedList.addAll(
      [EntryItem(1, 'A'), EntryItem(2, 'B'), EntryItem(3, 'C')]);
  print(linkedList.first); // 1 : A
  print(linkedList.last); // 3 : C

  // Add new item after first item.
  linkedList.first.insertAfter(EntryItem(15, 'E'));
  // Add new item before last item.
  linkedList.last.insertBefore(EntryItem(10, 'D'));
  // Iterate items.
  for (var entry in linkedList) {
    print(entry);
    // 1 : A
    // 15 : E
    // 2 : B
    // 10 : D
    // 3 : C
  }

  // Remove item using index from list.
  linkedList.elementAt(2).unlink();
  print(linkedList); // (1 : A, 15 : E, 10 : D, 3 : C)
  // Remove first item.
  linkedList.first.unlink();
  print(linkedList); // (15 : E, 10 : D, 3 : C)
  // Remove last item from list.
  linkedList.remove(linkedList.last);
  print(linkedList); // (15 : E, 10 : D)
  // Remove all items.
  linkedList.clear();
  print(linkedList.length); // 0
  print(linkedList.isEmpty); // true
}
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Iterable](../dart-core/iterable-class)\<E\>
    -   LinkedList

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[LinkedList](linkedlist/linkedlist)()
:   Constructs a new empty linked list.

Properties {#instance-properties}
----------

[first](linkedlist/first) → E

::: {.features}
read-only, override
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](linkedlist/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this collection has no elements.

[isNotEmpty](../dart-core/iterable/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](linkedlist/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, override
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](linkedlist/last) → E

::: {.features}
read-only, override
:::

Returns the last element.

[length](linkedlist/length) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Returns the number of elements in [this](linkedlist-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](linkedlist/single) → E

::: {.features}
read-only, override
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](linkedlist/add)(E entry) → void

Adds `entry` to the end of the linked list.

[addAll](linkedlist/addall)([Iterable](../dart-core/iterable-class)\<E\>
entries) → void

Adds `entries` to the end of the linked list.

[addFirst](linkedlist/addfirst)(E entry) → void

Adds `entry` to the beginning of the linked list.

[any](../dart-core/iterable/any)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](../dart-core/iterable/cast)\<R\>() →
[Iterable](../dart-core/iterable-class)\<R\>

::: {.features}
inherited
:::

Provides a view of this iterable as an iterable of `R` instances.

[clear](linkedlist/clear)() → void

Remove all elements from this linked list.

[contains](linkedlist/contains)([Object](../dart-core/object-class)?
entry) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether `entry` is a [LinkedListEntry](linkedlistentry-class) belonging
to this list.

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

[forEach](linkedlist/foreach)(void action(E entry)) → void

::: {.features}
override
:::

Call `action` with each entry in this linked list.

[join](../dart-core/iterable/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

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

[remove](linkedlist/remove)(E entry) → [bool](../dart-core/bool-class)

Removes `entry` from the linked list.

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

[toString](../dart-core/iterable/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns a string representation of (some of) the elements of `this`.

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
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList-class.html>
:::
