[dart:html](../dart-html/dart-html-library){._links-link}

AnchorElement class
===================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [Node](node-class)
    -   [Element](element-class)
    -   [HtmlElement](htmlelement-class)
    -   AnchorElement

Implemented types

:   -   [HtmlHyperlinkElementUtils](htmlhyperlinkelementutils-class)

Annotations

:   -   \@Native(\"HTMLAnchorElement\")

Constructors
------------

[AnchorElement](anchorelement/anchorelement)({[String](../dart-core/string-class)?
href})

::: {.constructor-modifier .features}
factory
:::

[AnchorElement.created](anchorelement/anchorelement.created)()

Constructor instantiated by the DOM when a custom element has been
created.

Properties {#instance-properties}
----------

[accessibleNode](element/accessiblenode) →
[AccessibleNode](accessiblenode-class)?

::: {.features}
read-only, inherited
:::

[assignedSlot](element/assignedslot) → [SlotElement](slotelement-class)?

::: {.features}
read-only, inherited
:::

[attributes](element/attributes) ↔
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

::: {.features}
read / write, inherited
:::

All attributes on this element.

[baseUri](node/baseuri) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'baseURI\'), read-only, inherited
:::

[borderEdge](element/borderedge) → [CssRect](cssrect-class)

::: {.features}
read-only, inherited
:::

Access the dimensions and position of this element\'s content + padding
+ border box.

[childNodes](node/childnodes) →
[List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\'), read-only, inherited
:::

A list of this node\'s children.

[children](element/children) ↔
[List](../dart-core/list-class)\<[Element](element-class)\>

::: {.features}
read / write, inherited
:::

List of the direct children of this element.

[classes](element/classes) ↔ [CssClassSet](cssclassset-class)

::: {.features}
read / write, inherited
:::

The set of CSS classes applied to this element.

[className](element/classname) ↔ [String](../dart-core/string-class)

::: {.features}
read / write, inherited
:::

[client](element/client) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only, inherited
:::

Gets the position of this element relative to the client area of the
page.

[clientHeight](element/clientheight) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[clientLeft](element/clientleft) → [int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

[clientTop](element/clienttop) → [int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

[clientWidth](element/clientwidth) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[computedName](element/computedname) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[computedRole](element/computedrole) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[contentEdge](element/contentedge) → [CssRect](cssrect-class)

::: {.features}
read-only, inherited
:::

Access this element\'s content position.

[contentEditable](element/contenteditable) ↔
[String](../dart-core/string-class)

::: {.features}
read / write, inherited
:::

[dataset](element/dataset) ↔
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

::: {.features}
read / write, inherited
:::

Allows access to all custom data attributes (data-\*) set on this
element.

[dir](element/dir) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[documentOffset](element/documentoffset) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only, inherited
:::

Provides the coordinates of the element relative to the top of the
document.

[download](anchorelement/download) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[draggable](element/draggable) ↔ [bool](../dart-core/bool-class)

::: {.features}
read / write, inherited
:::

Indicates whether the element can be dragged and dropped.

[firstChild](node/firstchild) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The first child of this node.

[hash](anchorelement/hash) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hidden](element/hidden) ↔ [bool](../dart-core/bool-class)

::: {.features}
read / write, inherited
:::

Indicates whether the element is not relevant to the page\'s current
state.

[host](anchorelement/host) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[hostname](anchorelement/hostname) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[href](anchorelement/href) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[hreflang](anchorelement/hreflang) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[id](element/id) ↔ [String](../dart-core/string-class)

::: {.features}
read / write, inherited
:::

[inert](element/inert) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write, inherited
:::

[innerHtml](element/innerhtml) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

Parses the HTML fragment and sets it as the contents of this element.

[innerText](element/innertext) ↔ [String](../dart-core/string-class)

::: {.features}
\@JSName(\'innerText\'), read / write, inherited
:::

[inputMode](element/inputmode) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[isConnected](node/isconnected) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[isContentEditable](element/iscontenteditable) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[lang](element/lang) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[lastChild](node/lastchild) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The last child of this node.

[localName](element/localname) → [String](../dart-core/string-class)

::: {.features}
\@Returns(\'String\'), read-only, inherited
:::

[marginEdge](element/marginedge) → [CssRect](cssrect-class)

::: {.features}
read-only, inherited
:::

Access the dimensions and position of this element\'s content + padding
+ border + margin box.

[namespaceUri](element/namespaceuri) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

A URI that identifies the XML namespace of this element.

[nextElementSibling](element/nextelementsibling) →
[Element](element-class)?

::: {.features}
read-only, inherited
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

[nonce](htmlelement/nonce) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[offset](element/offset) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only, inherited
:::

Gets the offset of this element relative to its offsetParent.

[offsetHeight](element/offsetheight) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[offsetLeft](element/offsetleft) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[offsetParent](element/offsetparent) → [Element](element-class)?

::: {.features}
read-only, inherited
:::

[offsetTop](element/offsettop) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[offsetWidth](element/offsetwidth) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[on](element/on) → [ElementEvents](elementevents-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](element/onabort) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `abort` events handled by this [Element](element-class).

[onBeforeCopy](element/onbeforecopy) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `beforecopy` events handled by this [Element](element-class).

[onBeforeCut](element/onbeforecut) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `beforecut` events handled by this [Element](element-class).

[onBeforePaste](element/onbeforepaste) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `beforepaste` events handled by this [Element](element-class).

[onBlur](element/onblur) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `blur` events handled by this [Element](element-class).

[onCanPlay](element/oncanplay) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onCanPlayThrough](element/oncanplaythrough) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onChange](element/onchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `change` events handled by this [Element](element-class).

[onClick](element/onclick) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `click` events handled by this [Element](element-class).

[onContextMenu](element/oncontextmenu) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `contextmenu` events handled by this [Element](element-class).

[onCopy](element/oncopy) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `copy` events handled by this [Element](element-class).

[onCut](element/oncut) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `cut` events handled by this [Element](element-class).

[onDoubleClick](element/ondoubleclick) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
\@DomName(\'Element.ondblclick\'), read-only, inherited
:::

Stream of `doubleclick` events handled by this [Element](element-class).

[onDrag](element/ondrag) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

A stream of `drag` events fired when this element currently being
dragged.

[onDragEnd](element/ondragend) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

A stream of `dragend` events fired when this element completes a drag
operation.

[onDragEnter](element/ondragenter) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

A stream of `dragenter` events fired when a dragged object is first
dragged over this element.

[onDragLeave](element/ondragleave) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

A stream of `dragleave` events fired when an object being dragged over
this element leaves this element\'s target area.

[onDragOver](element/ondragover) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

A stream of `dragover` events fired when a dragged object is currently
being dragged over this element.

[onDragStart](element/ondragstart) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

A stream of `dragstart` events fired when this element starts being
dragged.

[onDrop](element/ondrop) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

A stream of `drop` events fired when a dragged object is dropped on this
element.

[onDurationChange](element/ondurationchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onEmptied](element/onemptied) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onEnded](element/onended) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onError](element/onerror) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `error` events handled by this [Element](element-class).

[onFocus](element/onfocus) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `focus` events handled by this [Element](element-class).

[onFullscreenChange](element/onfullscreenchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `fullscreenchange` events handled by this
[Element](element-class).

[onFullscreenError](element/onfullscreenerror) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `fullscreenerror` events handled by this
[Element](element-class).

[onInput](element/oninput) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `input` events handled by this [Element](element-class).

[onInvalid](element/oninvalid) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `invalid` events handled by this [Element](element-class).

[onKeyDown](element/onkeydown) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `keydown` events handled by this [Element](element-class).

[onKeyPress](element/onkeypress) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `keypress` events handled by this [Element](element-class).

[onKeyUp](element/onkeyup) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `keyup` events handled by this [Element](element-class).

[onLoad](element/onload) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `load` events handled by this [Element](element-class).

[onLoadedData](element/onloadeddata) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onLoadedMetadata](element/onloadedmetadata) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onMouseDown](element/onmousedown) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mousedown` events handled by this [Element](element-class).

[onMouseEnter](element/onmouseenter) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseenter` events handled by this [Element](element-class).

[onMouseLeave](element/onmouseleave) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseleave` events handled by this [Element](element-class).

[onMouseMove](element/onmousemove) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mousemove` events handled by this [Element](element-class).

[onMouseOut](element/onmouseout) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseout` events handled by this [Element](element-class).

[onMouseOver](element/onmouseover) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseover` events handled by this [Element](element-class).

[onMouseUp](element/onmouseup) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseup` events handled by this [Element](element-class).

[onMouseWheel](element/onmousewheel) →
[ElementStream](elementstream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mousewheel` events handled by this [Element](element-class).

[onPaste](element/onpaste) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `paste` events handled by this [Element](element-class).

[onPause](element/onpause) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onPlay](element/onplay) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onPlaying](element/onplaying) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onRateChange](element/onratechange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onReset](element/onreset) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `reset` events handled by this [Element](element-class).

[onResize](element/onresize) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onScroll](element/onscroll) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `scroll` events handled by this [Element](element-class).

[onSearch](element/onsearch) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `search` events handled by this [Element](element-class).

[onSeeked](element/onseeked) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onSeeking](element/onseeking) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onSelect](element/onselect) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `select` events handled by this [Element](element-class).

[onSelectStart](element/onselectstart) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `selectstart` events handled by this [Element](element-class).

[onStalled](element/onstalled) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onSubmit](element/onsubmit) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `submit` events handled by this [Element](element-class).

[onSuspend](element/onsuspend) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onTimeUpdate](element/ontimeupdate) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onTouchCancel](element/ontouchcancel) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchcancel` events handled by this [Element](element-class).

[onTouchEnd](element/ontouchend) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchend` events handled by this [Element](element-class).

[onTouchEnter](element/ontouchenter) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchenter` events handled by this [Element](element-class).

[onTouchLeave](element/ontouchleave) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchleave` events handled by this [Element](element-class).

[onTouchMove](element/ontouchmove) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchmove` events handled by this [Element](element-class).

[onTouchStart](element/ontouchstart) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchstart` events handled by this [Element](element-class).

[onTransitionEnd](element/ontransitionend) →
[ElementStream](elementstream-class)\<[TransitionEvent](transitionevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only, inherited
:::

Stream of `transitionend` events handled by this
[Element](element-class).

[onVolumeChange](element/onvolumechange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onWaiting](element/onwaiting) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onWheel](element/onwheel) →
[ElementStream](elementstream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only, inherited
:::

[origin](anchorelement/origin) → [String](../dart-core/string-class)?

::: {.features}
read-only, override
:::

[outerHtml](element/outerhtml) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'outerHTML\'), read-only, inherited
:::

[ownerDocument](node/ownerdocument) → [Document](document-class)?

::: {.features}
read-only, inherited
:::

The document this node belongs to.

[paddingEdge](element/paddingedge) → [CssRect](cssrect-class)

::: {.features}
read-only, inherited
:::

Access the dimensions and position of this element\'s content + padding
box.

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

[password](anchorelement/password) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[pathname](anchorelement/pathname) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[port](anchorelement/port) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[previousElementSibling](element/previouselementsibling) →
[Element](element-class)?

::: {.features}
read-only, inherited
:::

[previousNode](node/previousnode) → [Node](node-class)?

::: {.features}
\@JSName(\'previousSibling\'), read-only, inherited
:::

The previous sibling node.

[protocol](anchorelement/protocol) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[referrerPolicy](anchorelement/referrerpolicy) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[rel](anchorelement/rel) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[scrollHeight](element/scrollheight) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[scrollLeft](element/scrollleft) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, inherited
:::

[scrollTop](element/scrolltop) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, inherited
:::

[scrollWidth](element/scrollwidth) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[search](anchorelement/search) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

[shadowRoot](element/shadowroot) → [ShadowRoot](shadowroot-class)?

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'25\'), read-only,
inherited
:::

The shadow root of this shadow host.

[slot](element/slot) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[spellcheck](element/spellcheck) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write, inherited
:::

[style](element/style) →
[CssStyleDeclaration](cssstyledeclaration-class)

::: {.features}
read-only, inherited
:::

[styleMap](element/stylemap) →
[StylePropertyMap](stylepropertymap-class)?

::: {.features}
read-only, inherited
:::

[tabIndex](element/tabindex) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write, inherited
:::

[tagName](element/tagname) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

[target](anchorelement/target) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[text](node/text) ↔ [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'textContent\'), \@JSName(\'textContent\'), read / write,
inherited
:::

All text within this node and its descendents.

[title](element/title) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[translate](element/translate) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write, inherited
:::

Specifies whether this element\'s text content changes when the page is
localized.

[type](anchorelement/type) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[username](anchorelement/username) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, override
:::

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[after](element/after)([Object](../dart-core/object-class) nodes) → void

::: {.features}
inherited
:::

[animate](element/animate)([Iterable](../dart-core/iterable-class)\<[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
dynamic\>\> frames, \[dynamic timing\]) → [Animation](animation-class)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'36\'), inherited
:::

Creates a new AnimationEffect object whose target element is the object
on which the method is called, and calls the play() method of the
AnimationTimeline object of the document timeline of the node document
of the element, passing the newly created AnimationEffect as the
argument to the method. Returns an Animation for the effect.

[append](node/append)([Node](node-class) node) → [Node](node-class)

::: {.features}
\@JSName(\'appendChild\'), inherited
:::

Adds a node to the end of the child [nodes](node/nodes) list of this
node.

[appendHtml](element/appendhtml)([String](../dart-core/string-class)
text, {[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) → void

::: {.features}
inherited
:::

Parses the specified text as HTML and adds the resulting node after the
last child of this element.

[appendText](element/appendtext)([String](../dart-core/string-class)
text) → void

::: {.features}
inherited
:::

Adds the specified text after the last child of this element.

[attached](element/attached)() → void

::: {.features}
inherited
:::

Called by the DOM when this element has been inserted into the live
document.

[attachShadow](element/attachshadow)([Map](../dart-core/map-class)
shadowRootInitDict) → [ShadowRoot](shadowroot-class)

::: {.features}
inherited
:::

[attributeChanged](element/attributechanged)([String](../dart-core/string-class)
name, [String](../dart-core/string-class) oldValue,
[String](../dart-core/string-class) newValue) → void

::: {.features}
inherited
:::

Called by the DOM whenever an attribute on this has been changed.

[before](element/before)([Object](../dart-core/object-class) nodes) →
void

::: {.features}
inherited
:::

[blur](element/blur)() → void

::: {.features}
inherited
:::

[click](element/click)() → void

::: {.features}
inherited
:::

[clone](node/clone)([bool](../dart-core/bool-class)? deep) →
[Node](node-class)

::: {.features}
\@JSName(\'cloneNode\'), inherited
:::

Returns a copy of this node.

[closest](element/closest)([String](../dart-core/string-class)
selectors) → [Element](element-class)?

::: {.features}
inherited
:::

[contains](node/contains)([Node](node-class)? other) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns true if this node contains the specified node.

[createFragment](element/createfragment)([String](../dart-core/string-class)?
html, {[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) →
[DocumentFragment](documentfragment-class)

::: {.features}
inherited
:::

Create a DocumentFragment from the HTML fragment and ensure that it
follows the sanitization rules specified by the validator or
treeSanitizer.

[createShadowRoot](element/createshadowroot)() →
[ShadowRoot](shadowroot-class)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'25\'), inherited
:::

Creates a new shadow root for this shadow host.

[detached](element/detached)() → void

::: {.features}
inherited
:::

Called by the DOM when this element has been removed from the live
document.

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[enteredView](element/enteredview){.deprecated}() → void

::: {.features}
inherited
:::

Deprecated\*: override [attached](element/attached) instead.

[focus](element/focus)() → void

::: {.features}
inherited
:::

[getAnimations](element/getanimations)() →
[List](../dart-core/list-class)\<[Animation](animation-class)\>

::: {.features}
inherited
:::

[getAttribute](element/getattribute)([String](../dart-core/string-class)
name) → [String](../dart-core/string-class)?

::: {.features}
inherited
:::

[getAttributeNames](element/getattributenames)() →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

[getAttributeNS](element/getattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name) →
[String](../dart-core/string-class)?

::: {.features}
inherited
:::

[getBoundingClientRect](element/getboundingclientrect)() →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

::: {.features}
\@Creates(\'\_DomRect\'), \@Returns(\'\_DomRect\|Null\'), inherited
:::

Returns the smallest bounding rectangle that encompasses this element\'s
padding, scrollbar, and border.

[getClientRects](element/getclientrects)() →
[List](../dart-core/list-class)\<[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>\>

::: {.features}
inherited
:::

[getComputedStyle](element/getcomputedstyle)(\[[String](../dart-core/string-class)?
pseudoElement\]) → [CssStyleDeclaration](cssstyledeclaration-class)

::: {.features}
inherited
:::

The set of all CSS values applied to this element, including inherited
and default values.

[getDestinationInsertionPoints](element/getdestinationinsertionpoints)()
→ [List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\'), inherited
:::

Returns a list of shadow DOM insertion points to which this element is
distributed.

[getElementsByClassName](element/getelementsbyclassname)([String](../dart-core/string-class)
classNames) → [List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Creates(\'NodeList\|HtmlCollection\'),
\@Returns(\'NodeList\|HtmlCollection\'), inherited
:::

Returns a list of nodes with the given class name inside this element.

[getNamespacedAttributes](element/getnamespacedattributes)([String](../dart-core/string-class)
namespace) →
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Gets a map for manipulating the attributes of a particular namespace.

[getRootNode](node/getrootnode)(\[[Map](../dart-core/map-class)?
options\]) → [Node](node-class)

::: {.features}
inherited
:::

[hasAttribute](element/hasattribute)([String](../dart-core/string-class)
name) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[hasAttributeNS](element/hasattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[hasChildNodes](node/haschildnodes)() → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns true if this node has any children.

[hasPointerCapture](element/haspointercapture)([int](../dart-core/int-class)
pointerId) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[insertAdjacentElement](element/insertadjacentelement)([String](../dart-core/string-class)
where, [Element](element-class) element) → [Element](element-class)

::: {.features}
inherited
:::

Inserts `element` into the DOM at the specified location.

[insertAdjacentHtml](element/insertadjacenthtml)([String](../dart-core/string-class)
where, [String](../dart-core/string-class) html,
{[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) → void

::: {.features}
inherited
:::

Parses text as an HTML fragment and inserts it into the DOM at the
specified location.

[insertAdjacentText](element/insertadjacenttext)([String](../dart-core/string-class)
where, [String](../dart-core/string-class) text) → void

::: {.features}
inherited
:::

Inserts text into the DOM at the specified location.

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

[leftView](element/leftview){.deprecated}() → void

::: {.features}
inherited
:::

Deprecated\*: override [detached](element/detached) instead.

[matches](element/matches)([String](../dart-core/string-class)
selectors) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks if this element matches the CSS selectors.

[matchesWithAncestors](element/matcheswithancestors)([String](../dart-core/string-class)
selectors) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks if this element or any of its parents match the CSS selectors.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[offsetTo](element/offsetto)([Element](element-class) parent) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
inherited
:::

Provides the offset of this element\'s [borderEdge](element/borderedge)
relative to the specified `parent`.

[querySelector](element/queryselector)([String](../dart-core/string-class)
selectors) → [Element](element-class)?

::: {.features}
inherited
:::

Finds the first descendant element of this element that matches the
specified group of selectors.

[querySelectorAll](element/queryselectorall)\<T extends
[Element](element-class)\>([String](../dart-core/string-class)
selectors) → [ElementList](elementlist-class)\<T\>

::: {.features}
inherited
:::

Finds all descendent elements of this element that match the specified
group of selectors.

[releasePointerCapture](element/releasepointercapture)([int](../dart-core/int-class)
pointerId) → void

::: {.features}
inherited
:::

[remove](node/remove)() → void

::: {.features}
inherited
:::

Removes this node from the DOM.

[removeAttribute](element/removeattribute)([String](../dart-core/string-class)
name) → void

::: {.features}
inherited
:::

[removeAttributeNS](element/removeattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name) → void

::: {.features}
inherited
:::

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

[requestFullscreen](element/requestfullscreen)(\[[Map](../dart-core/map-class)?
options\]) → [Future](../dart-async/future-class)\<void\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.SAFARI), inherited
:::

Displays this element fullscreen.

[requestPointerLock](element/requestpointerlock)() → void

::: {.features}
inherited
:::

[scroll](element/scroll)(\[dynamic options\_OR\_x,
[num](../dart-core/num-class)? y\]) → void

::: {.features}
inherited
:::

[scrollBy](element/scrollby)(\[dynamic options\_OR\_x,
[num](../dart-core/num-class)? y\]) → void

::: {.features}
inherited
:::

[scrollIntoView](element/scrollintoview)(\[[ScrollAlignment](scrollalignment-class)?
alignment\]) → void

::: {.features}
inherited
:::

Scrolls this element into view.

[scrollIntoViewIfNeeded](element/scrollintoviewifneeded)(\[[bool](../dart-core/bool-class)?
centerIfNeeded\]) → void

::: {.features}
inherited
:::

Nonstandard version of `scrollIntoView` that scrolls the current element
into the visible area of the browser window if it\'s not already within
the visible area of the browser window. If the element is already within
the visible area of the browser window, then no scrolling takes place.

[scrollTo](element/scrollto)(\[dynamic options\_OR\_x,
[num](../dart-core/num-class)? y\]) → void

::: {.features}
inherited
:::

[setApplyScroll](element/setapplyscroll)([String](../dart-core/string-class)
nativeScrollBehavior) →
[Future](../dart-async/future-class)\<[ScrollState](scrollstate-class)\>

::: {.features}
inherited
:::

[setAttribute](element/setattribute)([String](../dart-core/string-class)
name, [Object](../dart-core/object-class) value) → void

::: {.features}
inherited
:::

[setAttributeNS](element/setattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name,
[Object](../dart-core/object-class) value) → void

::: {.features}
inherited
:::

[setDistributeScroll](element/setdistributescroll)([String](../dart-core/string-class)
nativeScrollBehavior) →
[Future](../dart-async/future-class)\<[ScrollState](scrollstate-class)\>

::: {.features}
inherited
:::

[setInnerHtml](element/setinnerhtml)([String](../dart-core/string-class)?
html, {[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) → void

::: {.features}
inherited
:::

Parses the HTML fragment and sets it as the contents of this element.
This ensures that the generated content follows the sanitization rules
specified by the validator or treeSanitizer.

[setPointerCapture](element/setpointercapture)([int](../dart-core/int-class)
pointerId) → void

::: {.features}
inherited
:::

[toString](anchorelement/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
:::

The string representation of this element.

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
<https://api.dart.dev/stable/2.18.5/dart-html/AnchorElement-class.html>
:::
