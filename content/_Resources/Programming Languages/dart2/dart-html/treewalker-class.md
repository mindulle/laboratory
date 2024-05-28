[dart:html](../dart-html/dart-html-library){._links-link}

TreeWalker class
================

Annotations

:   -   \@Unstable()
    -   \@Native(\"TreeWalker\")

Constructors
------------

[TreeWalker](treewalker/treewalker)([Node](node-class) root,
[int](../dart-core/int-class) whatToShow)

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[currentNode](treewalker/currentnode) ↔ [Node](node-class)

::: {.features}
read / write
:::

[filter](treewalker/filter) → [NodeFilter](nodefilter-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[root](treewalker/root) → [Node](node-class)

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[whatToShow](treewalker/whattoshow) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[firstChild](treewalker/firstchild)() → [Node](node-class)?

[lastChild](treewalker/lastchild)() → [Node](node-class)?

[nextNode](treewalker/nextnode)() → [Node](node-class)?

[nextSibling](treewalker/nextsibling)() → [Node](node-class)?

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[parentNode](treewalker/parentnode)() → [Node](node-class)?

[previousNode](treewalker/previousnode)() → [Node](node-class)?

[previousSibling](treewalker/previoussibling)() → [Node](node-class)?

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
<https://api.dart.dev/stable/2.18.5/dart-html/TreeWalker-class.html>
:::
