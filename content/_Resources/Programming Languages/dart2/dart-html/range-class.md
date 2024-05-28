[dart:html](../dart-html/dart-html-library){._links-link}

Range class
===========

Annotations

:   -   \@Unstable()
    -   \@Native(\"Range\")

Constructors
------------

[Range](range/range)()

::: {.constructor-modifier .features}
factory
:::

[Range.fromPoint](range/range.frompoint)([Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>
point)

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[collapsed](range/collapsed) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[commonAncestorContainer](range/commonancestorcontainer) →
[Node](node-class)

::: {.features}
read-only
:::

[endContainer](range/endcontainer) → [Node](node-class)

::: {.features}
read-only
:::

[endOffset](range/endoffset) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

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

[startContainer](range/startcontainer) → [Node](node-class)

::: {.features}
read-only
:::

[startOffset](range/startoffset) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[cloneContents](range/clonecontents)() →
[DocumentFragment](documentfragment-class)

[cloneRange](range/clonerange)() → [Range](range-class)

[collapse](range/collapse)(\[[bool](../dart-core/bool-class)? toStart\])
→ void

[compareBoundaryPoints](range/compareboundarypoints)([int](../dart-core/int-class)
how, [Range](range-class) sourceRange) → [int](../dart-core/int-class)

[comparePoint](range/comparepoint)([Node](node-class) node,
[int](../dart-core/int-class) offset) → [int](../dart-core/int-class)

[createContextualFragment](range/createcontextualfragment)([String](../dart-core/string-class)
fragment) → [DocumentFragment](documentfragment-class)

[deleteContents](range/deletecontents)() → void

[detach](range/detach)() → void

[expand](range/expand)([String](../dart-core/string-class)? unit) → void

[extractContents](range/extractcontents)() →
[DocumentFragment](documentfragment-class)

[getBoundingClientRect](range/getboundingclientrect)() →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

[getClientRects](range/getclientrects)() →
[List](../dart-core/list-class)\<[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>\>

[insertNode](range/insertnode)([Node](node-class) node) → void

[isPointInRange](range/ispointinrange)([Node](node-class) node,
[int](../dart-core/int-class) offset) → [bool](../dart-core/bool-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[selectNode](range/selectnode)([Node](node-class) node) → void

[selectNodeContents](range/selectnodecontents)([Node](node-class) node)
→ void

[setEnd](range/setend)([Node](node-class) node,
[int](../dart-core/int-class) offset) → void

[setEndAfter](range/setendafter)([Node](node-class) node) → void

[setEndBefore](range/setendbefore)([Node](node-class) node) → void

[setStart](range/setstart)([Node](node-class) node,
[int](../dart-core/int-class) offset) → void

[setStartAfter](range/setstartafter)([Node](node-class) node) → void

[setStartBefore](range/setstartbefore)([Node](node-class) node) → void

[surroundContents](range/surroundcontents)([Node](node-class) newParent)
→ void

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

Static Properties
-----------------

[supportsCreateContextualFragment](range/supportscreatecontextualfragment)
→ [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if createContextualFragment is supported.

Constants
---------

[END\_TO\_END](range/end_to_end-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[END\_TO\_START](range/end_to_start-constant) → const [int](../dart-core/int-class)

:   <div>

    `3`

    </div>

[START\_TO\_END](range/start_to_end-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[START\_TO\_START](range/start_to_start-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Range-class.html>
:::
