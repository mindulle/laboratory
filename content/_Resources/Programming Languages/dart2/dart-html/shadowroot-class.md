[dart:html](../dart-html/dart-html-library){._links-link}

ShadowRoot class
================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [Node](node-class)
    -   [DocumentFragment](documentfragment-class)
    -   ShadowRoot

Implemented types

:   -   [DocumentOrShadowRoot](documentorshadowroot-class)

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME, \'26\')
    -   \@Native(\"ShadowRoot\")

Properties {#instance-properties}
----------

[activeElement](shadowroot/activeelement) → [Element](element-class)?

::: {.features}
read-only, override
:::

[applyAuthorStyles](shadowroot/applyauthorstyles){.deprecated} ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

[baseUri](node/baseuri) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'baseURI\'), read-only, inherited
:::

[childNodes](node/childnodes) →
[List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\'), read-only, inherited
:::

A list of this node\'s children.

[children](documentfragment/children) ↔
[List](../dart-core/list-class)\<[Element](element-class)\>

::: {.features}
read / write, inherited
:::

[delegatesFocus](shadowroot/delegatesfocus) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[firstChild](node/firstchild) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The first child of this node.

[fullscreenElement](shadowroot/fullscreenelement) →
[Element](element-class)?

::: {.features}
read-only, override
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[host](shadowroot/host) → [Element](element-class)?

::: {.features}
read-only
:::

[innerHtml](shadowroot/innerhtml) ↔ [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'innerHTML\'), \@JSName(\'innerHTML\'), read / write, override
:::

[isConnected](node/isconnected) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[lastChild](node/lastchild) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The last child of this node.

[mode](shadowroot/mode) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[nextNode](node/nextnode) → [Node](node-class)?

::: {.features}
\@JSName(\'nextSibling\'), read-only, inherited
:::

The next sibling node.

[nodeName](node/nodename) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

The name of this node.

[nodes](node/nodes) ↔
[List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
read / write, inherited
:::

A modifiable list of this node\'s children.

[nodeType](node/nodetype) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The type of node.

[nodeValue](node/nodevalue) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

The value of this node.

[olderShadowRoot](shadowroot/oldershadowroot) →
[ShadowRoot](shadowroot-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[ownerDocument](node/ownerdocument) → [Document](document-class)?

::: {.features}
read-only, inherited
:::

The document this node belongs to.

[parent](node/parent) → [Element](element-class)?

::: {.features}
\@JSName(\'parentElement\'), read-only, inherited
:::

The parent element of this node.

[parentNode](node/parentnode) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The parent node of this node.

[pointerLockElement](shadowroot/pointerlockelement) →
[Element](element-class)?

::: {.features}
read-only, override
:::

[previousNode](node/previousnode) → [Node](node-class)?

::: {.features}
\@JSName(\'previousSibling\'), read-only, inherited
:::

The previous sibling node.

[resetStyleInheritance](shadowroot/resetstyleinheritance){.deprecated} ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[styleSheets](shadowroot/stylesheets) →
[List](../dart-core/list-class)\<[StyleSheet](stylesheet-class)\>?

::: {.features}
\@Returns(\'\_StyleSheetList\'), \@Creates(\'\_StyleSheetList\'),
read-only, override
:::

[text](node/text) ↔ [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'textContent\'), \@JSName(\'textContent\'), read / write,
inherited
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
\@JSName(\'appendChild\'), inherited
:::

Adds a node to the end of the child [nodes](node/nodes) list of this
node.

[appendHtml](documentfragment/appendhtml)([String](../dart-core/string-class)
text, {[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) → void

::: {.features}
inherited
:::

Parses the specified text as HTML and adds the resulting node after the
last child of this document fragment.

[appendText](documentfragment/appendtext)([String](../dart-core/string-class)
text) → void

::: {.features}
inherited
:::

Adds the specified text as a text node after the last child of this
document fragment.

[clone](node/clone)([bool](../dart-core/bool-class)? deep) →
[Node](node-class)

::: {.features}
\@JSName(\'cloneNode\'), inherited
:::

Returns a copy of this node.

[contains](node/contains)([Node](node-class)? other) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns true if this node contains the specified node.

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[elementFromPoint](shadowroot/elementfrompoint)([int](../dart-core/int-class)
x, [int](../dart-core/int-class) y) → [Element](element-class)?

::: {.features}
override
:::

[elementsFromPoint](shadowroot/elementsfrompoint)([int](../dart-core/int-class)
x, [int](../dart-core/int-class) y) →
[List](../dart-core/list-class)\<[Element](element-class)\>

::: {.features}
override
:::

[getElementById](documentfragment/getelementbyid)([String](../dart-core/string-class)
elementId) → [Element](element-class)?

::: {.features}
inherited
:::

[getRootNode](node/getrootnode)(\[[Map](../dart-core/map-class)?
options\]) → [Node](node-class)

::: {.features}
inherited
:::

[getSelection](shadowroot/getselection)() →
[Selection](selection-class)?

::: {.features}
override
:::

[hasChildNodes](node/haschildnodes)() → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns true if this node has any children.

[insertAllBefore](node/insertallbefore)([Iterable](../dart-core/iterable-class)\<[Node](node-class)\>
newNodes, [Node](node-class) child) → void

::: {.features}
inherited
:::

Inserts all of the nodes into this node directly before child.

[insertBefore](node/insertbefore)([Node](node-class) node,
[Node](node-class)? child) → [Node](node-class)

::: {.features}
inherited
:::

Inserts the given node into this node directly before child. If child is
`null`, then the given node is inserted at the end of this node\'s child
nodes.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[querySelector](documentfragment/queryselector)([String](../dart-core/string-class)
selectors) → [Element](element-class)?

::: {.features}
inherited
:::

Finds the first descendant element of this document fragment that
matches the specified group of selectors.

[querySelectorAll](documentfragment/queryselectorall)\<T extends
[Element](element-class)\>([String](../dart-core/string-class)
selectors) → [ElementList](elementlist-class)\<T\>

::: {.features}
inherited
:::

Finds all descendant elements of this document fragment that match the
specified group of selectors.

[remove](node/remove)() → void

::: {.features}
inherited
:::

Removes this node from the DOM.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[replaceWith](node/replacewith)([Node](node-class) otherNode) →
[Node](node-class)

::: {.features}
inherited
:::

Replaces this node with another node.

[setInnerHtml](documentfragment/setinnerhtml)([String](../dart-core/string-class)?
html, {[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) → void

::: {.features}
inherited
:::

[toString](node/tostring)() → [String](../dart-core/string-class)

::: {.features}
inherited
:::

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

Static Properties
-----------------

[supported](shadowroot/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ShadowRoot-class.html>
:::
