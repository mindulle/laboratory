[dart:html](../dart-html/dart-html-library){._links-link}

Selection class
===============

Annotations

:   -   \@Native(\"Selection\")

Properties {#instance-properties}
----------

[anchorNode](selection/anchornode) → [Node](node-class)?

::: {.features}
read-only
:::

[anchorOffset](selection/anchoroffset) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[baseNode](selection/basenode) → [Node](node-class)?

::: {.features}
read-only
:::

[baseOffset](selection/baseoffset) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[extentNode](selection/extentnode) → [Node](node-class)?

::: {.features}
read-only
:::

[extentOffset](selection/extentoffset) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[focusNode](selection/focusnode) → [Node](node-class)?

::: {.features}
read-only
:::

[focusOffset](selection/focusoffset) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isCollapsed](selection/iscollapsed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[rangeCount](selection/rangecount) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[type](selection/type) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[addRange](selection/addrange)([Range](range-class) range) → void

[collapse](selection/collapse)([Node](node-class)? node,
\[[int](../dart-core/int-class)? offset\]) → void

[collapseToEnd](selection/collapsetoend)() → void

[collapseToStart](selection/collapsetostart)() → void

[containsNode](selection/containsnode)([Node](node-class) node,
\[[bool](../dart-core/bool-class)? allowPartialContainment\]) →
[bool](../dart-core/bool-class)

[deleteFromDocument](selection/deletefromdocument)() → void

[empty](selection/empty)() → void

[extend](selection/extend)([Node](node-class) node,
\[[int](../dart-core/int-class)? offset\]) → void

[getRangeAt](selection/getrangeat)([int](../dart-core/int-class) index)
→ [Range](range-class)

[modify](selection/modify)([String](../dart-core/string-class)? alter,
[String](../dart-core/string-class)? direction,
[String](../dart-core/string-class)? granularity) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeAllRanges](selection/removeallranges)() → void

[removeRange](selection/removerange)([Range](range-class) range) → void

[selectAllChildren](selection/selectallchildren)([Node](node-class)
node) → void

[setBaseAndExtent](selection/setbaseandextent)([Node](node-class)?
baseNode, [int](../dart-core/int-class) baseOffset, [Node](node-class)?
extentNode, [int](../dart-core/int-class) extentOffset) → void

[setPosition](selection/setposition)([Node](node-class)? node,
\[[int](../dart-core/int-class)? offset\]) → void

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
<https://api.dart.dev/stable/2.18.5/dart-html/Selection-class.html>
:::
