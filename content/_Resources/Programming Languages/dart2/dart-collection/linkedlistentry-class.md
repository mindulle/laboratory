[dart:collection](../dart-collection/dart-collection-library){._links-link}

LinkedListEntry\<E extends LinkedListEntry\<E\>\> class
=======================================================

An object that can be an element in a [LinkedList](linkedlist-class).

All elements of a `LinkedList` must extend this class. The class
provides the internal links that link elements together in the
`LinkedList`, and a reference to the linked list itself that an element
is currently part of.

An entry can be in at most one linked list at a time. While an entry is
in a linked list, the [list](linkedlistentry/list) property points to
that linked list, and otherwise the `list` property is `null`.

When created, an entry is not in any linked list.

Constructors
------------

[LinkedListEntry](linkedlistentry/linkedlistentry)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[list](linkedlistentry/list) → [LinkedList](linkedlist-class)\<E\>?

::: {.features}
read-only
:::

The linked list containing this element.

[next](linkedlistentry/next) → E?

::: {.features}
read-only
:::

The successor of this element in its linked list.

[previous](linkedlistentry/previous) → E?

::: {.features}
read-only
:::

The predecessor of this element in its linked list.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[insertAfter](linkedlistentry/insertafter)(E entry) → void

Insert an element after this element in this element\'s linked list.

[insertBefore](linkedlistentry/insertbefore)(E entry) → void

Insert an element before this element in this element\'s linked list.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[unlink](linkedlistentry/unlink)() → void

Unlink the element from its linked list.

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
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedListEntry-class.html>
:::
