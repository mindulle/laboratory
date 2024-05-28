[dart:html](../dart-html/dart-html-library){._links-link}

HtmlDocument class
==================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [Node](node-class)
    -   [Document](document-class)
    -   HtmlDocument

Annotations

:   -   \@Native(\"HTMLDocument\")

Properties {#instance-properties}
----------

[activeElement](document/activeelement) → [Element](element-class)?

::: {.features}
read-only, inherited
:::

[addressSpace](document/addressspace) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[baseUri](node/baseuri) → [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'baseURI\'), read-only, inherited
:::

[body](htmldocument/body) ↔ [BodyElement](bodyelement-class)?

::: {.features}
read / write
:::

[childNodes](node/childnodes) →
[List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\'), read-only, inherited
:::

A list of this node\'s children.

[contentType](document/contenttype) →
[String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[cookie](document/cookie) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[currentScript](document/currentscript) →
[ScriptElement](scriptelement-class)?

::: {.features}
read-only, inherited
:::

[documentElement](document/documentelement) → [Element](element-class)?

::: {.features}
read-only, inherited
:::

[domain](document/domain) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[firstChild](node/firstchild) → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The first child of this node.

[fonts](document/fonts) → [FontFaceSet](fontfaceset-class)?

::: {.features}
read-only, inherited
:::

[fullscreenElement](document/fullscreenelement) →
[Element](element-class)?

::: {.features}
read-only, inherited
:::

[fullscreenEnabled](document/fullscreenenabled) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[head](htmldocument/head) → [HeadElement](headelement-class)?

::: {.features}
read-only
:::

[hidden](document/hidden) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[implementation](document/implementation) →
[DomImplementation](domimplementation-class)?

::: {.features}
read-only, inherited
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

[lastModified](htmldocument/lastmodified) →
[String](../dart-core/string-class)?

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

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onAbort](document/onabort) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `abort` events handled by this [Document](document-class).

[onBeforeCopy](document/onbeforecopy) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `beforecopy` events handled by this
[Document](document-class).

[onBeforeCut](document/onbeforecut) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `beforecut` events handled by this [Document](document-class).

[onBeforePaste](document/onbeforepaste) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `beforepaste` events handled by this
[Document](document-class).

[onBlur](document/onblur) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `blur` events handled by this [Document](document-class).

[onCanPlay](document/oncanplay) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onCanPlayThrough](document/oncanplaythrough) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onChange](document/onchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `change` events handled by this [Document](document-class).

[onClick](document/onclick) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `click` events handled by this [Document](document-class).

[onContextMenu](document/oncontextmenu) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `contextmenu` events handled by this
[Document](document-class).

[onCopy](document/oncopy) →
[Stream](../dart-async/stream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `copy` events handled by this [Document](document-class).

[onCut](document/oncut) →
[Stream](../dart-async/stream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `cut` events handled by this [Document](document-class).

[onDoubleClick](document/ondoubleclick) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
\@DomName(\'Document.ondblclick\'), read-only, inherited
:::

Stream of `doubleclick` events handled by this
[Document](document-class).

[onDrag](document/ondrag) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `drag` events handled by this [Document](document-class).

[onDragEnd](document/ondragend) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `dragend` events handled by this [Document](document-class).

[onDragEnter](document/ondragenter) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `dragenter` events handled by this [Document](document-class).

[onDragLeave](document/ondragleave) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `dragleave` events handled by this [Document](document-class).

[onDragOver](document/ondragover) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `dragover` events handled by this [Document](document-class).

[onDragStart](document/ondragstart) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `dragstart` events handled by this [Document](document-class).

[onDrop](document/ondrop) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `drop` events handled by this [Document](document-class).

[onDurationChange](document/ondurationchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onEmptied](document/onemptied) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onEnded](document/onended) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onError](document/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `error` events handled by this [Document](document-class).

[onFocus](document/onfocus) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `focus` events handled by this [Document](document-class).

[onFullscreenChange](document/onfullscreenchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `fullscreenchange` events handled by this
[Document](document-class).

[onFullscreenError](document/onfullscreenerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `fullscreenerror` events handled by this
[Document](document-class).

[onInput](document/oninput) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `input` events handled by this [Document](document-class).

[onInvalid](document/oninvalid) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `invalid` events handled by this [Document](document-class).

[onKeyDown](document/onkeydown) →
[Stream](../dart-async/stream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `keydown` events handled by this [Document](document-class).

[onKeyPress](document/onkeypress) →
[Stream](../dart-async/stream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `keypress` events handled by this [Document](document-class).

[onKeyUp](document/onkeyup) →
[Stream](../dart-async/stream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `keyup` events handled by this [Document](document-class).

[onLoad](document/onload) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `load` events handled by this [Document](document-class).

[onLoadedData](document/onloadeddata) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onLoadedMetadata](document/onloadedmetadata) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onMouseDown](document/onmousedown) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mousedown` events handled by this [Document](document-class).

[onMouseEnter](document/onmouseenter) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseenter` events handled by this
[Document](document-class).

[onMouseLeave](document/onmouseleave) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseleave` events handled by this
[Document](document-class).

[onMouseMove](document/onmousemove) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mousemove` events handled by this [Document](document-class).

[onMouseOut](document/onmouseout) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseout` events handled by this [Document](document-class).

[onMouseOver](document/onmouseover) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseover` events handled by this [Document](document-class).

[onMouseUp](document/onmouseup) →
[Stream](../dart-async/stream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mouseup` events handled by this [Document](document-class).

[onMouseWheel](document/onmousewheel) →
[Stream](../dart-async/stream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `mousewheel` events handled by this
[Document](document-class).

[onPaste](document/onpaste) →
[Stream](../dart-async/stream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `paste` events handled by this [Document](document-class).

[onPause](document/onpause) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onPlay](document/onplay) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onPlaying](document/onplaying) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onPointerLockChange](document/onpointerlockchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onPointerLockError](document/onpointerlockerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onRateChange](document/onratechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onReadyStateChange](document/onreadystatechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `readystatechange` events handled by this
[Document](document-class).

[onReset](document/onreset) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `reset` events handled by this [Document](document-class).

[onResize](document/onresize) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onScroll](document/onscroll) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `scroll` events handled by this [Document](document-class).

[onSearch](document/onsearch) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `search` events handled by this [Document](document-class).

[onSecurityPolicyViolation](document/onsecuritypolicyviolation) →
[Stream](../dart-async/stream-class)\<[SecurityPolicyViolationEvent](securitypolicyviolationevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `securitypolicyviolation` events handled by this
[Document](document-class).

[onSeeked](document/onseeked) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onSeeking](document/onseeking) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onSelect](document/onselect) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `select` events handled by this [Document](document-class).

[onSelectionChange](document/onselectionchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `selectionchange` events handled by this
[Document](document-class).

[onSelectStart](document/onselectstart) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `selectstart` events handled by this
[Document](document-class).

[onStalled](document/onstalled) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onSubmit](document/onsubmit) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

Stream of `submit` events handled by this [Document](document-class).

[onSuspend](document/onsuspend) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onTimeUpdate](document/ontimeupdate) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onTouchCancel](document/ontouchcancel) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchcancel` events handled by this
[Document](document-class).

[onTouchEnd](document/ontouchend) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchend` events handled by this [Document](document-class).

[onTouchMove](document/ontouchmove) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchmove` events handled by this [Document](document-class).

[onTouchStart](document/ontouchstart) →
[Stream](../dart-async/stream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only, inherited
:::

Stream of `touchstart` events handled by this
[Document](document-class).

[onVisibilityChange](htmldocument/onvisibilitychange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'), read-only
:::

[onVolumeChange](document/onvolumechange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[onWaiting](document/onwaiting) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[origin](document/origin) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

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

[pointerLockElement](document/pointerlockelement) →
[Element](element-class)?

::: {.features}
read-only, inherited
:::

[preferredStylesheetSet](htmldocument/preferredstylesheetset) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[previousNode](node/previousnode) → [Node](node-class)?

::: {.features}
\@JSName(\'previousSibling\'), read-only, inherited
:::

The previous sibling node.

[readyState](document/readystate) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[referrer](htmldocument/referrer) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[rootElement](document/rootelement) →
[SvgSvgElement](../dart-svg/svgsvgelement-class)?

::: {.features}
read-only, inherited
:::

[rootScroller](document/rootscroller) ↔ [Element](element-class)?

::: {.features}
read / write, inherited
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[scrollingElement](document/scrollingelement) →
[Element](element-class)?

::: {.features}
read-only, inherited
:::

[selectedStylesheetSet](htmldocument/selectedstylesheetset) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[styleSheets](htmldocument/stylesheets) →
[List](../dart-core/list-class)\<[StyleSheet](stylesheet-class)\>?

::: {.features}
read-only
:::

[suborigin](document/suborigin) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[supportsRegister](document/supportsregister){.deprecated} →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

*Deprecated*: use
[supportsRegisterElement](document/supportsregisterelement) instead.

[supportsRegisterElement](document/supportsregisterelement) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Checks if [registerElement](document/registerelement) is supported on
the current platform.

[text](node/text) ↔ [String](../dart-core/string-class)?

::: {.features}
\@JSName(\'textContent\'), \@JSName(\'textContent\'), read / write,
inherited
:::

All text within this node and its descendents.

[timeline](document/timeline) →
[DocumentTimeline](documenttimeline-class)?

::: {.features}
read-only, inherited
:::

[title](htmldocument/title) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

[visibilityState](document/visibilitystate) →
[String](../dart-core/string-class)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'), read-only, inherited
:::

[window](document/window) → [WindowBase](windowbase-class)?

::: {.features}
read-only, inherited
:::

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[adoptNode](document/adoptnode)([Node](node-class) node) →
[Node](node-class)

::: {.features}
inherited
:::

[append](node/append)([Node](node-class) node) → [Node](node-class)

::: {.features}
\@JSName(\'appendChild\'), inherited
:::

Adds a node to the end of the child [nodes](node/nodes) list of this
node.

[caretRangeFromPoint](htmldocument/caretrangefrompoint)([int](../dart-core/int-class)?
x, [int](../dart-core/int-class)? y) → [Range](range-class)

::: {.features}
\@Unstable()
:::

UNSTABLE: Chrome-only - create a Range from the given point.

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

[createDocumentFragment](document/createdocumentfragment)() →
[DocumentFragment](documentfragment-class)

::: {.features}
inherited
:::

[createElement](document/createelement)([String](../dart-core/string-class)
tagName, \[[String](../dart-core/string-class)? typeExtension\]) →
[Element](element-class)

::: {.features}
inherited
:::

[createElementNS](document/createelementns)([String](../dart-core/string-class)
namespaceURI, [String](../dart-core/string-class) qualifiedName,
\[[String](../dart-core/string-class)? typeExtension\]) →
[Element](element-class)

::: {.features}
inherited
:::

[createElementUpgrader](htmldocument/createelementupgrader)([Type](../dart-core/type-class)
type, {[String](../dart-core/string-class)? extendsTag}) →
[ElementUpgrader](elementupgrader-class)

Creates an element upgrader which can be used to change the Dart wrapper
type for elements.

[createRange](document/createrange)() → [Range](range-class)

::: {.features}
inherited
:::

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[elementFromPoint](htmldocument/elementfrompoint)([int](../dart-core/int-class)
x, [int](../dart-core/int-class) y) → [Element](element-class)?

[elementsFromPoint](document/elementsfrompoint)([int](../dart-core/int-class)
x, [int](../dart-core/int-class) y) →
[List](../dart-core/list-class)\<[Element](element-class)\>

::: {.features}
inherited
:::

[execCommand](document/execcommand)([String](../dart-core/string-class)
commandId, \[[bool](../dart-core/bool-class)? showUI,
[String](../dart-core/string-class)? value\]) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[exitFullscreen](htmldocument/exitfullscreen)() → void

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI), override
:::

Returns page to standard layout.

[exitPointerLock](document/exitpointerlock)() → void

::: {.features}
inherited
:::

[getAnimations](document/getanimations)() →
[List](../dart-core/list-class)\<[Animation](animation-class)\>

::: {.features}
inherited
:::

[getElementById](document/getelementbyid)([String](../dart-core/string-class)
elementId) → [Element](element-class)?

::: {.features}
inherited
:::

[getElementsByClassName](document/getelementsbyclassname)([String](../dart-core/string-class)
classNames) → [List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Creates(\'NodeList\|HtmlCollection\'),
\@Returns(\'NodeList\|HtmlCollection\'), inherited
:::

[getElementsByName](document/getelementsbyname)([String](../dart-core/string-class)
elementName) → [List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Creates(\'NodeList\|HtmlCollection\'),
\@Returns(\'NodeList\|HtmlCollection\'), inherited
:::

[getElementsByTagName](document/getelementsbytagname)([String](../dart-core/string-class)
localName) → [List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
\@Creates(\'NodeList\|HtmlCollection\'),
\@Returns(\'NodeList\|HtmlCollection\'), inherited
:::

[getRootNode](node/getrootnode)(\[[Map](../dart-core/map-class)?
options\]) → [Node](node-class)

::: {.features}
inherited
:::

[hasChildNodes](node/haschildnodes)() → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns true if this node has any children.

[importNode](document/importnode)([Node](node-class) node,
\[[bool](../dart-core/bool-class)? deep\]) → [Node](node-class)

::: {.features}
inherited
:::

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

[queryCommandEnabled](document/querycommandenabled)([String](../dart-core/string-class)
commandId) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[queryCommandIndeterm](document/querycommandindeterm)([String](../dart-core/string-class)
commandId) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[queryCommandState](document/querycommandstate)([String](../dart-core/string-class)
commandId) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[queryCommandSupported](document/querycommandsupported)([String](../dart-core/string-class)
commandId) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[queryCommandValue](document/querycommandvalue)([String](../dart-core/string-class)
commandId) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

[querySelector](document/queryselector)([String](../dart-core/string-class)
selectors) → [Element](element-class)?

::: {.features}
inherited
:::

Finds the first descendant element of this document that matches the
specified group of selectors.

[querySelectorAll](document/queryselectorall)\<T extends
[Element](element-class)\>([String](../dart-core/string-class)
selectors) → [ElementList](elementlist-class)\<T\>

::: {.features}
inherited
:::

Finds all descendant elements of this document that match the specified
group of selectors.

[register](htmldocument/register){.deprecated}([String](../dart-core/string-class)
tag, [Type](../dart-core/type-class) customElementClass,
{[String](../dart-core/string-class)? extendsTag}) → void

Deprecated\*: use [registerElement](document/registerelement) instead.

[registerElement](document/registerelement)([String](../dart-core/string-class)
tag, [Type](../dart-core/type-class) customElementClass,
{[String](../dart-core/string-class)? extendsTag}) → void

::: {.features}
inherited
:::

[registerElement2](htmldocument/registerelement2)([String](../dart-core/string-class)
tag, \[[Map](../dart-core/map-class)? options\]) →
[Function](../dart-core/function-class)

::: {.features}
override
:::

Register a custom subclass of Element to be instantiatable by the DOM.

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

Constants
---------

[visibilityChangeEvent](htmldocument/visibilitychangeevent-constant) →
const
[EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\')
:::

Static factory designed to expose `visibilitychange` events to event
handlers that are not necessarily instances of
[Document](document-class).

<div>

`const _CustomEventStreamProvider<Event>(_determineVisibilityChangeEventType)`

</div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HtmlDocument-class.html>
:::
