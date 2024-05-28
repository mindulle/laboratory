[dart:html](../dart-html/dart-html-library){._links-link}

Node class
==========

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   Node

Implementers

:   -   [CharacterData](characterdata-class)
    -   [Document](document-class)
    -   [DocumentFragment](documentfragment-class)
    -   [Element](element-class)

Annotations

:   -   \@Native(\"Node\")

Properties {#instance-properties}
----------

[baseUri](node/baseuri) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'baseURI\'), read-only
:::

[childNodes](node/childnodes) →
[List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\'), read-only
:::

A list of this node\'s children.

[firstChild](node/firstchild) → [Node](node-class)?

::: {.features}
read-only
:::

The first child of this node.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isConnected](node/isconnected) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[lastChild](node/lastchild) → [Node](node-class)?

::: {.features}
read-only
:::

The last child of this node.

[nextNode](node/nextnode) → [Node](node-class)?

::: {.features}
\@JSName(\'nextSibling\'), read-only
:::

The next sibling node.

[nodeName](node/nodename) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

The name of this node.

[nodes](node/nodes) ↔
[List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
read / write
:::

A modifiable list of this node\'s children.

[nodeType](node/nodetype) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The type of node.

[nodeValue](node/nodevalue) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

The value of this node.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[ownerDocument](node/ownerdocument) → [Document](document-class)?

::: {.features}
read-only
:::

The document this node belongs to.

[parent](node/parent) → [Element](element-class)?

::: {.features}
\@JSName(\'parentElement\'), read-only
:::

The parent element of this node.

[parentNode](node/parentnode) → [Node](node-class)?

::: {.features}
read-only
:::

The parent node of this node.

[previousNode](node/previousnode) → [Node](node-class)?

::: {.features}
\@JSName(\'previousSibling\'), read-only
:::

The previous sibling node.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[text](node/text) ↔ [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'textContent\'), \@JSName(\'textContent\'), read / write
:::

All text within this node and its descendents.

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[append](node/append)([Node](node-class) node) → [Node](node-class)

::: {.features}
\@JSName(\'appendChild\')
:::

Adds a node to the end of the child [nodes](node/nodes) list of this
node.

[clone](node/clone)([bool](../dart-core/bool-class)? deep) →
[Node](node-class)

::: {.features}
\@JSName(\'cloneNode\')
:::

Returns a copy of this node.

[contains](node/contains)([Node](node-class)? other) →
[bool](../dart-core/bool-class)

Returns true if this node contains the specified node.

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getRootNode](node/getrootnode)(\[[Map](../dart-core/map-class)?
options\]) → [Node](node-class)

[hasChildNodes](node/haschildnodes)() → [bool](../dart-core/bool-class)

Returns true if this node has any children.

[insertAllBefore](node/insertallbefore)([Iterable](../dart-core/iterable-class)\<[Node](node-class)\>
newNodes, [Node](node-class) child) → void

Inserts all of the nodes into this node directly before child.

[insertBefore](node/insertbefore)([Node](node-class) node,
[Node](node-class)? child) → [Node](node-class)

Inserts the given node into this node directly before child. If child is
`null`, then the given node is inserted at the end of this node\'s child
nodes.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[remove](node/remove)() → void

Removes this node from the DOM.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[replaceWith](node/replacewith)([Node](node-class) otherNode) →
[Node](node-class)

Replaces this node with another node.

[toString](node/tostring)() → [String](../dart-core/string-class)

Print out a String representation of this Node.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Constants
---------

[ATTRIBUTE\_NODE](node/attribute_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[CDATA\_SECTION\_NODE](node/cdata_section_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `4`

    </div>

[COMMENT\_NODE](node/comment_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `8`

    </div>

[DOCUMENT\_FRAGMENT\_NODE](node/document_fragment_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `11`

    </div>

[DOCUMENT\_NODE](node/document_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `9`

    </div>

[DOCUMENT\_TYPE\_NODE](node/document_type_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `10`

    </div>

[ELEMENT\_NODE](node/element_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[ENTITY\_NODE](node/entity_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `6`

    </div>

[ENTITY\_REFERENCE\_NODE](node/entity_reference_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `5`

    </div>

[NOTATION\_NODE](node/notation_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `12`

    </div>

[PROCESSING\_INSTRUCTION\_NODE](node/processing_instruction_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `7`

    </div>

[TEXT\_NODE](node/text_node-constant) → const [int](../dart-core/int-class)

:   <div>

    `3`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node-class.html>
:::
