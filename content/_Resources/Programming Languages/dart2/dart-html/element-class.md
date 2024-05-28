[dart:html](../dart-html/dart-html-library){._links-link}

Element class
=============

An abstract class, which all HTML elements extend.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [Node](node-class)
    -   Element

Implemented types

:   -   [ParentNode](parentnode-class)
    -   [ChildNode](childnode-class)
    -   [NonDocumentTypeChildNode](nondocumenttypechildnode-class)
    -   [GlobalEventHandlers](globaleventhandlers-class)

Implementers

:   -   [HtmlElement](htmlelement-class)
    -   [InputElementBase](inputelementbase-class)
    -   [MathMLElement](mathmlelement-class)
    -   [SvgElement](../dart-svg/svgelement-class)

Annotations

:   -   \@Native(\"Element\")

Constructors
------------

[Element.a](element/element.a)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<a>` element.

[Element.article](element/element.article)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<article>` element.

[Element.aside](element/element.aside)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<aside>` element.

[Element.audio](element/element.audio)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<audio>` element.

[Element.br](element/element.br)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<br>` element.

[Element.canvas](element/element.canvas)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<canvas>` element.

[Element.created](element/element.created)()

Custom element creation constructor.

[Element.div](element/element.div)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<div>` element.

[Element.footer](element/element.footer)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<footer>` element.

[Element.header](element/element.header)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<header>` element.

[Element.hr](element/element.hr)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<hr>` element.

[Element.html](element/element.html)([String](../dart-core/string-class)?
html, {[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer})

::: {.constructor-modifier .features}
factory
:::

Creates an HTML element from a valid fragment of HTML.

[Element.iframe](element/element.iframe)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<iframe>` element.

[Element.img](element/element.img)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<img>` element.

[Element.li](element/element.li)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<li>` element.

[Element.nav](element/element.nav)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<nav>` element.

[Element.ol](element/element.ol)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<ol>` element.

[Element.option](element/element.option)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<option>` element.

[Element.p](element/element.p)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<p>` element.

[Element.pre](element/element.pre)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<pre>` element.

[Element.section](element/element.section)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<section>` element.

[Element.select](element/element.select)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<select>` element.

[Element.span](element/element.span)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<span>` element.

[Element.svg](element/element.svg)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<svg>` element.

[Element.table](element/element.table)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<table>` element.

[Element.tag](element/element.tag)([String](../dart-core/string-class)
tag, \[[String](../dart-core/string-class)? typeExtension\])

::: {.constructor-modifier .features}
factory
:::

Creates the HTML element specified by the tag name.

[Element.td](element/element.td)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<td>` element.

[Element.textarea](element/element.textarea)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<textarea>` element.

[Element.th](element/element.th)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<th>` element.

[Element.tr](element/element.tr)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<tr>` element.

[Element.ul](element/element.ul)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<ul>` element.

[Element.video](element/element.video)()

::: {.constructor-modifier .features}
factory
:::

Creates a new `<video>` element.

Properties {#instance-properties}
----------

[accessibleNode](element/accessiblenode) →
[AccessibleNode](accessiblenode-class)?

::: {.features}
read-only
:::

[assignedSlot](element/assignedslot) → [SlotElement](slotelement-class)?

::: {.features}
read-only
:::

[attributes](element/attributes) ↔
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

::: {.features}
read / write
:::

All attributes on this element.

[baseUri](node/baseuri) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'baseURI\'), read-only, inherited
:::

[borderEdge](element/borderedge) → [CssRect](cssrect-class)

::: {.features}
read-only
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
read / write
:::

List of the direct children of this element.

[classes](element/classes) ↔ [CssClassSet](cssclassset-class)

::: {.features}
read / write
:::

The set of CSS classes applied to this element.

[className](element/classname) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[client](element/client) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

Gets the position of this element relative to the client area of the
page.

[clientHeight](element/clientheight) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[clientLeft](element/clientleft) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[clientTop](element/clienttop) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[clientWidth](element/clientwidth) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[computedName](element/computedname) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[computedRole](element/computedrole) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[contentEdge](element/contentedge) → [CssRect](cssrect-class)

::: {.features}
read-only
:::

Access this element\'s content position.

[contentEditable](element/contenteditable) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

[dataset](element/dataset) ↔
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

::: {.features}
read / write
:::

Allows access to all custom data attributes (data-\*) set on this
element.

[dir](element/dir) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[documentOffset](element/documentoffset) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

Provides the coordinates of the element relative to the top of the
document.

[draggable](element/draggable) ↔ [bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Indicates whether the element can be dragged and dropped.

[firstChild](node/firstchild) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The first child of this node.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hidden](element/hidden) ↔ [bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Indicates whether the element is not relevant to the page\'s current
state.

[id](element/id) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[inert](element/inert) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[innerHtml](element/innerhtml) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

Parses the HTML fragment and sets it as the contents of this element.

[innerText](element/innertext) ↔ [String](../dart-core/string-class)

::: {.features}
\@JSName(\'innerText\'), read / write
:::

[inputMode](element/inputmode) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[isConnected](node/isconnected) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[isContentEditable](element/iscontenteditable) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[lang](element/lang) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[lastChild](node/lastchild) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The last child of this node.

[localName](element/localname) → [String](../dart-core/string-class)

::: {.features}
\@Returns(\'String\'), read-only
:::

[marginEdge](element/marginedge) → [CssRect](cssrect-class)

::: {.features}
read-only
:::

Access the dimensions and position of this element\'s content + padding
+ border + margin box.

[namespaceUri](element/namespaceuri) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

A URI that identifies the XML namespace of this element.

[nextElementSibling](element/nextelementsibling) →
[Element](element-class)?

::: {.features}
read-only, override
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

[offset](element/offset) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

Gets the offset of this element relative to its offsetParent.

[offsetHeight](element/offsetheight) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[offsetLeft](element/offsetleft) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[offsetParent](element/offsetparent) → [Element](element-class)?

::: {.features}
read-only
:::

[offsetTop](element/offsettop) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[offsetWidth](element/offsetwidth) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[on](element/on) → [ElementEvents](elementevents-class)

::: {.features}
read-only, override
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](element/onabort) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `abort` events handled by this [Element](element-class).

[onBeforeCopy](element/onbeforecopy) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `beforecopy` events handled by this [Element](element-class).

[onBeforeCut](element/onbeforecut) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `beforecut` events handled by this [Element](element-class).

[onBeforePaste](element/onbeforepaste) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `beforepaste` events handled by this [Element](element-class).

[onBlur](element/onblur) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `blur` events handled by this [Element](element-class).

[onCanPlay](element/oncanplay) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onCanPlayThrough](element/oncanplaythrough) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onChange](element/onchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `change` events handled by this [Element](element-class).

[onClick](element/onclick) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `click` events handled by this [Element](element-class).

[onContextMenu](element/oncontextmenu) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `contextmenu` events handled by this [Element](element-class).

[onCopy](element/oncopy) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only
:::

Stream of `copy` events handled by this [Element](element-class).

[onCut](element/oncut) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only
:::

Stream of `cut` events handled by this [Element](element-class).

[onDoubleClick](element/ondoubleclick) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
\@DomName(\'Element.ondblclick\'), read-only, override
:::

Stream of `doubleclick` events handled by this [Element](element-class).

[onDrag](element/ondrag) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

A stream of `drag` events fired when this element currently being
dragged.

[onDragEnd](element/ondragend) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

A stream of `dragend` events fired when this element completes a drag
operation.

[onDragEnter](element/ondragenter) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

A stream of `dragenter` events fired when a dragged object is first
dragged over this element.

[onDragLeave](element/ondragleave) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

A stream of `dragleave` events fired when an object being dragged over
this element leaves this element\'s target area.

[onDragOver](element/ondragover) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

A stream of `dragover` events fired when a dragged object is currently
being dragged over this element.

[onDragStart](element/ondragstart) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

A stream of `dragstart` events fired when this element starts being
dragged.

[onDrop](element/ondrop) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

A stream of `drop` events fired when a dragged object is dropped on this
element.

[onDurationChange](element/ondurationchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onEmptied](element/onemptied) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onEnded](element/onended) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onError](element/onerror) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `error` events handled by this [Element](element-class).

[onFocus](element/onfocus) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `focus` events handled by this [Element](element-class).

[onFullscreenChange](element/onfullscreenchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `fullscreenchange` events handled by this
[Element](element-class).

[onFullscreenError](element/onfullscreenerror) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `fullscreenerror` events handled by this
[Element](element-class).

[onInput](element/oninput) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `input` events handled by this [Element](element-class).

[onInvalid](element/oninvalid) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `invalid` events handled by this [Element](element-class).

[onKeyDown](element/onkeydown) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, override
:::

Stream of `keydown` events handled by this [Element](element-class).

[onKeyPress](element/onkeypress) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, override
:::

Stream of `keypress` events handled by this [Element](element-class).

[onKeyUp](element/onkeyup) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, override
:::

Stream of `keyup` events handled by this [Element](element-class).

[onLoad](element/onload) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `load` events handled by this [Element](element-class).

[onLoadedData](element/onloadeddata) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onLoadedMetadata](element/onloadedmetadata) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onMouseDown](element/onmousedown) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mousedown` events handled by this [Element](element-class).

[onMouseEnter](element/onmouseenter) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseenter` events handled by this [Element](element-class).

[onMouseLeave](element/onmouseleave) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseleave` events handled by this [Element](element-class).

[onMouseMove](element/onmousemove) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mousemove` events handled by this [Element](element-class).

[onMouseOut](element/onmouseout) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseout` events handled by this [Element](element-class).

[onMouseOver](element/onmouseover) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseover` events handled by this [Element](element-class).

[onMouseUp](element/onmouseup) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mouseup` events handled by this [Element](element-class).

[onMouseWheel](element/onmousewheel) →
[ElementStream](elementstream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only, override
:::

Stream of `mousewheel` events handled by this [Element](element-class).

[onPaste](element/onpaste) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only
:::

Stream of `paste` events handled by this [Element](element-class).

[onPause](element/onpause) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onPlay](element/onplay) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onPlaying](element/onplaying) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onRateChange](element/onratechange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onReset](element/onreset) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `reset` events handled by this [Element](element-class).

[onResize](element/onresize) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onScroll](element/onscroll) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `scroll` events handled by this [Element](element-class).

[onSearch](element/onsearch) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `search` events handled by this [Element](element-class).

[onSeeked](element/onseeked) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onSeeking](element/onseeking) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onSelect](element/onselect) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `select` events handled by this [Element](element-class).

[onSelectStart](element/onselectstart) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `selectstart` events handled by this [Element](element-class).

[onStalled](element/onstalled) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onSubmit](element/onsubmit) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

Stream of `submit` events handled by this [Element](element-class).

[onSuspend](element/onsuspend) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onTimeUpdate](element/ontimeupdate) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onTouchCancel](element/ontouchcancel) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchcancel` events handled by this [Element](element-class).

[onTouchEnd](element/ontouchend) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchend` events handled by this [Element](element-class).

[onTouchEnter](element/ontouchenter) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchenter` events handled by this [Element](element-class).

[onTouchLeave](element/ontouchleave) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchleave` events handled by this [Element](element-class).

[onTouchMove](element/ontouchmove) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchmove` events handled by this [Element](element-class).

[onTouchStart](element/ontouchstart) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, override
:::

Stream of `touchstart` events handled by this [Element](element-class).

[onTransitionEnd](element/ontransitionend) →
[ElementStream](elementstream-class)\<[TransitionEvent](transitionevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only
:::

Stream of `transitionend` events handled by this
[Element](element-class).

[onVolumeChange](element/onvolumechange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onWaiting](element/onwaiting) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only, override
:::

[onWheel](element/onwheel) →
[ElementStream](elementstream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only, override
:::

[outerHtml](element/outerhtml) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'outerHTML\'), read-only
:::

[ownerDocument](node/ownerdocument) → [Document](document-class)?

::: {.features}
read-only, inherited
:::

The document this node belongs to.

[paddingEdge](element/paddingedge) → [CssRect](cssrect-class)

::: {.features}
read-only
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

[previousElementSibling](element/previouselementsibling) →
[Element](element-class)?

::: {.features}
read-only, override
:::

[previousNode](node/previousnode) → [Node](node-class)?

::: {.features}
\@JSName(\'previousSibling\'), read-only, inherited
:::

The previous sibling node.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[scrollHeight](element/scrollheight) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[scrollLeft](element/scrollleft) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

[scrollTop](element/scrolltop) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

[scrollWidth](element/scrollwidth) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[shadowRoot](element/shadowroot) → [ShadowRoot](shadowroot-class)?

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'25\'), read-only
:::

The shadow root of this shadow host.

[slot](element/slot) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[spellcheck](element/spellcheck) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

[style](element/style) →
[CssStyleDeclaration](cssstyledeclaration-class)

::: {.features}
read-only
:::

[styleMap](element/stylemap) →
[StylePropertyMap](stylepropertymap-class)?

::: {.features}
read-only
:::

[tabIndex](element/tabindex) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write
:::

[tagName](element/tagname) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[text](node/text) ↔ [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'textContent\'), \@JSName(\'textContent\'), read / write,
inherited
:::

All text within this node and its descendents.

[title](element/title) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[translate](element/translate) ↔ [bool](../dart-core/bool-class)?

::: {.features}
read / write
:::

Specifies whether this element\'s text content changes when the page is
localized.

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
override
:::

[animate](element/animate)([Iterable](../dart-core/iterable-class)\<[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
dynamic\>\> frames, \[dynamic timing\]) → [Animation](animation-class)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'36\')
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

Parses the specified text as HTML and adds the resulting node after the
last child of this element.

[appendText](element/appendtext)([String](../dart-core/string-class)
text) → void

Adds the specified text after the last child of this element.

[attached](element/attached)() → void

Called by the DOM when this element has been inserted into the live
document.

[attachShadow](element/attachshadow)([Map](../dart-core/map-class)
shadowRootInitDict) → [ShadowRoot](shadowroot-class)

[attributeChanged](element/attributechanged)([String](../dart-core/string-class)
name, [String](../dart-core/string-class) oldValue,
[String](../dart-core/string-class) newValue) → void

Called by the DOM whenever an attribute on this has been changed.

[before](element/before)([Object](../dart-core/object-class) nodes) →
void

::: {.features}
override
:::

[blur](element/blur)() → void

[click](element/click)() → void

[clone](node/clone)([bool](../dart-core/bool-class)? deep) →
[Node](node-class)

::: {.features}
\@JSName(\'cloneNode\'), inherited
:::

Returns a copy of this node.

[closest](element/closest)([String](../dart-core/string-class)
selectors) → [Element](element-class)?

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

Create a DocumentFragment from the HTML fragment and ensure that it
follows the sanitization rules specified by the validator or
treeSanitizer.

[createShadowRoot](element/createshadowroot)() →
[ShadowRoot](shadowroot-class)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'25\')
:::

Creates a new shadow root for this shadow host.

[detached](element/detached)() → void

Called by the DOM when this element has been removed from the live
document.

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[enteredView](element/enteredview){.deprecated}() → void

Deprecated\*: override [attached](element/attached) instead.

[focus](element/focus)() → void

[getAnimations](element/getanimations)() →
[List](../dart-core/list-class)\<[Animation](animation-class)\>

[getAttribute](element/getattribute)([String](../dart-core/string-class)
name) → [String](../dart-core/string-class)?

[getAttributeNames](element/getattributenames)() →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

[getAttributeNS](element/getattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name) →
[String](../dart-core/string-class)?

[getBoundingClientRect](element/getboundingclientrect)() →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

::: {.features}
\@Creates(\'\_DomRect\'), \@Returns(\'\_DomRect\|Null\')
:::

Returns the smallest bounding rectangle that encompasses this element\'s
padding, scrollbar, and border.

[getClientRects](element/getclientrects)() →
[List](../dart-core/list-class)\<[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>\>

[getComputedStyle](element/getcomputedstyle)(\[[String](../dart-core/string-class)?
pseudoElement\]) → [CssStyleDeclaration](cssstyledeclaration-class)

The set of all CSS values applied to this element, including inherited
and default values.

[getDestinationInsertionPoints](element/getdestinationinsertionpoints)()
→ [List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\')
:::

Returns a list of shadow DOM insertion points to which this element is
distributed.

[getElementsByClassName](element/getelementsbyclassname)([String](../dart-core/string-class)
classNames) → [List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Creates(\'NodeList\|HtmlCollection\'),
\@Returns(\'NodeList\|HtmlCollection\')
:::

Returns a list of nodes with the given class name inside this element.

[getNamespacedAttributes](element/getnamespacedattributes)([String](../dart-core/string-class)
namespace) →
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

Gets a map for manipulating the attributes of a particular namespace.

[getRootNode](node/getrootnode)(\[[Map](../dart-core/map-class)?
options\]) → [Node](node-class)

::: {.features}
inherited
:::

[hasAttribute](element/hasattribute)([String](../dart-core/string-class)
name) → [bool](../dart-core/bool-class)

[hasAttributeNS](element/hasattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name) →
[bool](../dart-core/bool-class)

[hasChildNodes](node/haschildnodes)() → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns true if this node has any children.

[hasPointerCapture](element/haspointercapture)([int](../dart-core/int-class)
pointerId) → [bool](../dart-core/bool-class)

[insertAdjacentElement](element/insertadjacentelement)([String](../dart-core/string-class)
where, [Element](element-class) element) → [Element](element-class)

Inserts `element` into the DOM at the specified location.

[insertAdjacentHtml](element/insertadjacenthtml)([String](../dart-core/string-class)
where, [String](../dart-core/string-class) html,
{[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) → void

Parses text as an HTML fragment and inserts it into the DOM at the
specified location.

[insertAdjacentText](element/insertadjacenttext)([String](../dart-core/string-class)
where, [String](../dart-core/string-class) text) → void

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

Deprecated\*: override [detached](element/detached) instead.

[matches](element/matches)([String](../dart-core/string-class)
selectors) → [bool](../dart-core/bool-class)

Checks if this element matches the CSS selectors.

[matchesWithAncestors](element/matcheswithancestors)([String](../dart-core/string-class)
selectors) → [bool](../dart-core/bool-class)

Checks if this element or any of its parents match the CSS selectors.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[offsetTo](element/offsetto)([Element](element-class) parent) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

Provides the offset of this element\'s [borderEdge](element/borderedge)
relative to the specified `parent`.

[querySelector](element/queryselector)([String](../dart-core/string-class)
selectors) → [Element](element-class)?

::: {.features}
override
:::

Finds the first descendant element of this element that matches the
specified group of selectors.

[querySelectorAll](element/queryselectorall)\<T extends
[Element](element-class)\>([String](../dart-core/string-class)
selectors) → [ElementList](elementlist-class)\<T\>

Finds all descendent elements of this element that match the specified
group of selectors.

[releasePointerCapture](element/releasepointercapture)([int](../dart-core/int-class)
pointerId) → void

[remove](node/remove)() → void

::: {.features}
inherited
:::

Removes this node from the DOM.

[removeAttribute](element/removeattribute)([String](../dart-core/string-class)
name) → void

[removeAttributeNS](element/removeattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name) → void

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
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

Displays this element fullscreen.

[requestPointerLock](element/requestpointerlock)() → void

[scroll](element/scroll)(\[dynamic options\_OR\_x,
[num](../dart-core/num-class)? y\]) → void

[scrollBy](element/scrollby)(\[dynamic options\_OR\_x,
[num](../dart-core/num-class)? y\]) → void

[scrollIntoView](element/scrollintoview)(\[[ScrollAlignment](scrollalignment-class)?
alignment\]) → void

Scrolls this element into view.

[scrollIntoViewIfNeeded](element/scrollintoviewifneeded)(\[[bool](../dart-core/bool-class)?
centerIfNeeded\]) → void

Nonstandard version of `scrollIntoView` that scrolls the current element
into the visible area of the browser window if it\'s not already within
the visible area of the browser window. If the element is already within
the visible area of the browser window, then no scrolling takes place.

[scrollTo](element/scrollto)(\[dynamic options\_OR\_x,
[num](../dart-core/num-class)? y\]) → void

[setApplyScroll](element/setapplyscroll)([String](../dart-core/string-class)
nativeScrollBehavior) →
[Future](../dart-async/future-class)\<[ScrollState](scrollstate-class)\>

[setAttribute](element/setattribute)([String](../dart-core/string-class)
name, [Object](../dart-core/object-class) value) → void

[setAttributeNS](element/setattributens)([String](../dart-core/string-class)?
namespaceURI, [String](../dart-core/string-class) name,
[Object](../dart-core/object-class) value) → void

[setDistributeScroll](element/setdistributescroll)([String](../dart-core/string-class)
nativeScrollBehavior) →
[Future](../dart-async/future-class)\<[ScrollState](scrollstate-class)\>

[setInnerHtml](element/setinnerhtml)([String](../dart-core/string-class)?
html, {[NodeValidator](nodevalidator-class)? validator,
[NodeTreeSanitizer](nodetreesanitizer-class)? treeSanitizer}) → void

Parses the HTML fragment and sets it as the contents of this element.
This ensures that the generated content follows the sanitization rules
specified by the validator or treeSanitizer.

[setPointerCapture](element/setpointercapture)([int](../dart-core/int-class)
pointerId) → void

[toString](element/tostring)() → [String](../dart-core/string-class)

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

Static Methods
--------------

[isTagSupported](element/istagsupported)([String](../dart-core/string-class) tag) → [bool](../dart-core/bool-class)
:   Checks to see if the tag name is supported by the current platform.

Constants
---------

[abortEvent](element/abortevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `abort` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('abort')`

</div>

[beforeCopyEvent](element/beforecopyevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `beforecopy` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('beforecopy')`

</div>

[beforeCutEvent](element/beforecutevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `beforecut` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('beforecut')`

</div>

[beforePasteEvent](element/beforepasteevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `beforepaste` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('beforepaste')`

</div>

[blurEvent](element/blurevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `blur` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('blur')`

</div>

[canPlayEvent](element/canplayevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('canplay')`

</div>

[canPlayThroughEvent](element/canplaythroughevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('canplaythrough')`

</div>

[changeEvent](element/changeevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `change` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('change')`

</div>

[clickEvent](element/clickevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `click` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('click')`

</div>

[contextMenuEvent](element/contextmenuevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `contextmenu` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('contextmenu')`

</div>

[copyEvent](element/copyevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[ClipboardEvent](clipboardevent-class)\>

Static factory designed to expose `copy` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<ClipboardEvent>('copy')`

</div>

[cutEvent](element/cutevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[ClipboardEvent](clipboardevent-class)\>

Static factory designed to expose `cut` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<ClipboardEvent>('cut')`

</div>

[doubleClickEvent](element/doubleclickevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

::: {.features}
\@DomName(\'Element.dblclickEvent\')
:::

Static factory designed to expose `doubleclick` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('dblclick')`

</div>

[dragEndEvent](element/dragendevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

A stream of `dragend` events fired when an element completes a drag
operation.

<div>

`const EventStreamProvider<MouseEvent>('dragend')`

</div>

[dragEnterEvent](element/dragenterevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

A stream of `dragenter` events fired when a dragged object is first
dragged over an element.

<div>

`const EventStreamProvider<MouseEvent>('dragenter')`

</div>

[dragEvent](element/dragevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

A stream of `drag` events fired when an element is currently being
dragged.

<div>

`const EventStreamProvider<MouseEvent>('drag')`

</div>

[dragLeaveEvent](element/dragleaveevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

A stream of `dragleave` events fired when an object being dragged over
an element leaves the element\'s target area.

<div>

`const EventStreamProvider<MouseEvent>('dragleave')`

</div>

[dragOverEvent](element/dragoverevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

A stream of `dragover` events fired when a dragged object is currently
being dragged over an element.

<div>

`const EventStreamProvider<MouseEvent>('dragover')`

</div>

[dragStartEvent](element/dragstartevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

A stream of `dragstart` events for a dragged element whose drag has
begun.

<div>

`const EventStreamProvider<MouseEvent>('dragstart')`

</div>

[dropEvent](element/dropevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

A stream of `drop` events fired when a dragged object is dropped on an
element.

<div>

`const EventStreamProvider<MouseEvent>('drop')`

</div>

[durationChangeEvent](element/durationchangeevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('durationchange')`

</div>

[emptiedEvent](element/emptiedevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('emptied')`

</div>

[endedEvent](element/endedevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('ended')`

</div>

[errorEvent](element/errorevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `error` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('error')`

</div>

[focusEvent](element/focusevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `focus` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('focus')`

</div>

[fullscreenChangeEvent](element/fullscreenchangeevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

Static factory designed to expose `fullscreenchange` events to event
handlers that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('webkitfullscreenchange')`

</div>

[fullscreenErrorEvent](element/fullscreenerrorevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::

Static factory designed to expose `fullscreenerror` events to event
handlers that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('webkitfullscreenerror')`

</div>

[inputEvent](element/inputevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `input` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('input')`

</div>

[invalidEvent](element/invalidevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `invalid` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('invalid')`

</div>

[keyDownEvent](element/keydownevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[KeyboardEvent](keyboardevent-class)\>

Static factory designed to expose `keydown` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<KeyboardEvent>('keydown')`

</div>

[keyPressEvent](element/keypressevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[KeyboardEvent](keyboardevent-class)\>

Static factory designed to expose `keypress` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<KeyboardEvent>('keypress')`

</div>

[keyUpEvent](element/keyupevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[KeyboardEvent](keyboardevent-class)\>

Static factory designed to expose `keyup` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<KeyboardEvent>('keyup')`

</div>

[loadedDataEvent](element/loadeddataevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('loadeddata')`

</div>

[loadedMetadataEvent](element/loadedmetadataevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('loadedmetadata')`

</div>

[loadEvent](element/loadevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `load` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('load')`

</div>

[mouseDownEvent](element/mousedownevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `mousedown` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('mousedown')`

</div>

[mouseEnterEvent](element/mouseenterevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `mouseenter` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('mouseenter')`

</div>

[mouseLeaveEvent](element/mouseleaveevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `mouseleave` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('mouseleave')`

</div>

[mouseMoveEvent](element/mousemoveevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `mousemove` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('mousemove')`

</div>

[mouseOutEvent](element/mouseoutevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `mouseout` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('mouseout')`

</div>

[mouseOverEvent](element/mouseoverevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `mouseover` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('mouseover')`

</div>

[mouseUpEvent](element/mouseupevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[MouseEvent](mouseevent-class)\>

Static factory designed to expose `mouseup` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<MouseEvent>('mouseup')`

</div>

[mouseWheelEvent](element/mousewheelevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[WheelEvent](wheelevent-class)\>

Static factory designed to expose `mousewheel` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const _CustomEventStreamProvider<WheelEvent>(Element._determineMouseWheelEventType)`

</div>

[pasteEvent](element/pasteevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[ClipboardEvent](clipboardevent-class)\>

Static factory designed to expose `paste` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<ClipboardEvent>('paste')`

</div>

[pauseEvent](element/pauseevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('pause')`

</div>

[playEvent](element/playevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('play')`

</div>

[playingEvent](element/playingevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('playing')`

</div>

[rateChangeEvent](element/ratechangeevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('ratechange')`

</div>

[resetEvent](element/resetevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `reset` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('reset')`

</div>

[resizeEvent](element/resizeevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('resize')`

</div>

[scrollEvent](element/scrollevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `scroll` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('scroll')`

</div>

[searchEvent](element/searchevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `search` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('search')`

</div>

[seekedEvent](element/seekedevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('seeked')`

</div>

[seekingEvent](element/seekingevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('seeking')`

</div>

[selectEvent](element/selectevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `select` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('select')`

</div>

[selectStartEvent](element/selectstartevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `selectstart` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('selectstart')`

</div>

[stalledEvent](element/stalledevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('stalled')`

</div>

[submitEvent](element/submitevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

Static factory designed to expose `submit` events to event handlers that
are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<Event>('submit')`

</div>

[suspendEvent](element/suspendevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('suspend')`

</div>

[timeUpdateEvent](element/timeupdateevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('timeupdate')`

</div>

[touchCancelEvent](element/touchcancelevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[TouchEvent](touchevent-class)\>

Static factory designed to expose `touchcancel` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<TouchEvent>('touchcancel')`

</div>

[touchEndEvent](element/touchendevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[TouchEvent](touchevent-class)\>

Static factory designed to expose `touchend` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<TouchEvent>('touchend')`

</div>

[touchEnterEvent](element/touchenterevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[TouchEvent](touchevent-class)\>

Static factory designed to expose `touchenter` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<TouchEvent>('touchenter')`

</div>

[touchLeaveEvent](element/touchleaveevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[TouchEvent](touchevent-class)\>

Static factory designed to expose `touchleave` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<TouchEvent>('touchleave')`

</div>

[touchMoveEvent](element/touchmoveevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[TouchEvent](touchevent-class)\>

Static factory designed to expose `touchmove` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<TouchEvent>('touchmove')`

</div>

[touchStartEvent](element/touchstartevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[TouchEvent](touchevent-class)\>

Static factory designed to expose `touchstart` events to event handlers
that are not necessarily instances of [Element](element-class).

<div>

`const EventStreamProvider<TouchEvent>('touchstart')`

</div>

[transitionEndEvent](element/transitionendevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[TransitionEvent](transitionevent-class)\>

Static factory designed to expose `transitionend` events to event
handlers that are not necessarily instances of [Element](element-class).

<div>

`const _CustomEventStreamProvider<TransitionEvent>(Element._determineTransitionEventType)`

</div>

[volumeChangeEvent](element/volumechangeevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('volumechange')`

</div>

[waitingEvent](element/waitingevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

<div>

`const EventStreamProvider<Event>('waiting')`

</div>

[wheelEvent](element/wheelevent-constant) → const
[EventStreamProvider](eventstreamprovider-class)\<[WheelEvent](wheelevent-class)\>

<div>

`const EventStreamProvider<WheelEvent>('wheel')`

</div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element-class.html>
:::
