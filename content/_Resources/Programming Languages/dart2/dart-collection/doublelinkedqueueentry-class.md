[dart:collection](../dart-collection/dart-collection-library){._links-link}

DoubleLinkedQueueEntry\<E\> class
=================================

An entry in a doubly linked list.

Such an entry contains an element and a link to the previous or next
entries, if any.

Constructors
------------

[DoubleLinkedQueueEntry](doublelinkedqueueentry/doublelinkedqueueentry)(E element)
:   Creates a new entry with the given
    [element](doublelinkedqueueentry/element).

Properties {#instance-properties}
----------

[element](doublelinkedqueueentry/element) ↔ E

::: {.features}
read / write
:::

The element of the entry in the queue.

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

[append](doublelinkedqueueentry/append)(E e) → void

Appends the given element `e` as entry just after this entry.

[nextEntry](doublelinkedqueueentry/nextentry)() →
[DoubleLinkedQueueEntry](doublelinkedqueueentry-class)\<E\>?

The next entry, or `null` if there is none.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[prepend](doublelinkedqueueentry/prepend)(E e) → void

Prepends the given `e` as entry just before this entry.

[previousEntry](doublelinkedqueueentry/previousentry)() →
[DoubleLinkedQueueEntry](doublelinkedqueueentry-class)\<E\>?

The previous entry, or `null` if there is none.

[remove](doublelinkedqueueentry/remove)() → E

Removes this entry from any chain of entries it is part of.

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
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueueEntry-class.html>
:::
