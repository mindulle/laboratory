[dart:html](../dart-html/dart-html-library){._links-link}

ElementList\<T extends Element\> class
======================================

An immutable list containing HTML elements. This list contains some
additional methods when compared to regular lists for ease of CSS
manipulation on a group of elements.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [ListBase](../dart-collection/listbase-class)\<T\>
    -   ElementList

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[ElementList](elementlist/elementlist)()

Properties {#instance-properties}
----------

[borderEdge](elementlist/borderedge) → [CssRect](cssrect-class)

::: {.features}
read-only
:::

Access dimensions and position of the first [Element](element-class)\'s
content + padding + border box in this list.

[classes](elementlist/classes) ↔ [CssClassSet](cssclassset-class)

::: {.features}
read / write
:::

The union of all CSS classes applied to the elements in this list.

[contentEdge](elementlist/contentedge) → [CssRect](cssrect-class)

::: {.features}
read-only
:::

Access dimensions and position of the [Element](element-class)s in this
list.

[first](../dart-collection/listmixin/first) ↔ T

::: {.features}
read / write, inherited
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](../dart-collection/listmixin/isempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](../dart-collection/listmixin/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](../dart-collection/listmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<T\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](../dart-collection/listmixin/last) ↔ T

::: {.features}
read / write, inherited
:::

Returns the last element.

[length](../dart-core/list/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, inherited
:::

The number of objects in this list.

[marginEdge](elementlist/marginedge) → [CssRect](cssrect-class)

::: {.features}
read-only
:::

Access dimensions and position of the first [Element](element-class)\'s
content + padding + border + margin box in this list.

[onAbort](elementlist/onabort) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `abort` events handled by this [Element](element-class).

[onBeforeCopy](elementlist/onbeforecopy) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `beforecopy` events handled by this [Element](element-class).

[onBeforeCut](elementlist/onbeforecut) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `beforecut` events handled by this [Element](element-class).

[onBeforePaste](elementlist/onbeforepaste) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `beforepaste` events handled by this [Element](element-class).

[onBlur](elementlist/onblur) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `blur` events handled by this [Element](element-class).

[onCanPlay](elementlist/oncanplay) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onCanPlayThrough](elementlist/oncanplaythrough) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onChange](elementlist/onchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `change` events handled by this [Element](element-class).

[onClick](elementlist/onclick) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `click` events handled by this [Element](element-class).

[onContextMenu](elementlist/oncontextmenu) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `contextmenu` events handled by this [Element](element-class).

[onCopy](elementlist/oncopy) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only
:::

Stream of `copy` events handled by this [Element](element-class).

[onCut](elementlist/oncut) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only
:::

Stream of `cut` events handled by this [Element](element-class).

[onDoubleClick](elementlist/ondoubleclick) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
\@DomName(\'Element.ondblclick\'), read-only
:::

Stream of `doubleclick` events handled by this [Element](element-class).

[onDrag](elementlist/ondrag) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

A stream of `drag` events fired when this element currently being
dragged.

[onDragEnd](elementlist/ondragend) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

A stream of `dragend` events fired when this element completes a drag
operation.

[onDragEnter](elementlist/ondragenter) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

A stream of `dragenter` events fired when a dragged object is first
dragged over this element.

[onDragLeave](elementlist/ondragleave) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

A stream of `dragleave` events fired when an object being dragged over
this element leaves this element\'s target area.

[onDragOver](elementlist/ondragover) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

A stream of `dragover` events fired when a dragged object is currently
being dragged over this element.

[onDragStart](elementlist/ondragstart) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

A stream of `dragstart` events fired when this element starts being
dragged.

[onDrop](elementlist/ondrop) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

A stream of `drop` events fired when a dragged object is dropped on this
element.

[onDurationChange](elementlist/ondurationchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onEmptied](elementlist/onemptied) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onEnded](elementlist/onended) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onError](elementlist/onerror) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `error` events handled by this [Element](element-class).

[onFocus](elementlist/onfocus) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `focus` events handled by this [Element](element-class).

[onFullscreenChange](elementlist/onfullscreenchange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `fullscreenchange` events handled by this
[Element](element-class).

[onFullscreenError](elementlist/onfullscreenerror) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `fullscreenerror` events handled by this
[Element](element-class).

[onInput](elementlist/oninput) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `input` events handled by this [Element](element-class).

[onInvalid](elementlist/oninvalid) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `invalid` events handled by this [Element](element-class).

[onKeyDown](elementlist/onkeydown) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only
:::

Stream of `keydown` events handled by this [Element](element-class).

[onKeyPress](elementlist/onkeypress) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only
:::

Stream of `keypress` events handled by this [Element](element-class).

[onKeyUp](elementlist/onkeyup) →
[ElementStream](elementstream-class)\<[KeyboardEvent](keyboardevent-class)\>

::: {.features}
read-only
:::

Stream of `keyup` events handled by this [Element](element-class).

[onLoad](elementlist/onload) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `load` events handled by this [Element](element-class).

[onLoadedData](elementlist/onloadeddata) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onLoadedMetadata](elementlist/onloadedmetadata) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onMouseDown](elementlist/onmousedown) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `mousedown` events handled by this [Element](element-class).

[onMouseEnter](elementlist/onmouseenter) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `mouseenter` events handled by this [Element](element-class).

[onMouseLeave](elementlist/onmouseleave) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `mouseleave` events handled by this [Element](element-class).

[onMouseMove](elementlist/onmousemove) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `mousemove` events handled by this [Element](element-class).

[onMouseOut](elementlist/onmouseout) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `mouseout` events handled by this [Element](element-class).

[onMouseOver](elementlist/onmouseover) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `mouseover` events handled by this [Element](element-class).

[onMouseUp](elementlist/onmouseup) →
[ElementStream](elementstream-class)\<[MouseEvent](mouseevent-class)\>

::: {.features}
read-only
:::

Stream of `mouseup` events handled by this [Element](element-class).

[onMouseWheel](elementlist/onmousewheel) →
[ElementStream](elementstream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only
:::

Stream of `mousewheel` events handled by this [Element](element-class).

[onPaste](elementlist/onpaste) →
[ElementStream](elementstream-class)\<[ClipboardEvent](clipboardevent-class)\>

::: {.features}
read-only
:::

Stream of `paste` events handled by this [Element](element-class).

[onPause](elementlist/onpause) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onPlay](elementlist/onplay) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onPlaying](elementlist/onplaying) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onRateChange](elementlist/onratechange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onReset](elementlist/onreset) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `reset` events handled by this [Element](element-class).

[onResize](elementlist/onresize) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onScroll](elementlist/onscroll) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `scroll` events handled by this [Element](element-class).

[onSearch](elementlist/onsearch) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `search` events handled by this [Element](element-class).

[onSeeked](elementlist/onseeked) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onSeeking](elementlist/onseeking) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onSelect](elementlist/onselect) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `select` events handled by this [Element](element-class).

[onSelectStart](elementlist/onselectstart) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `selectstart` events handled by this [Element](element-class).

[onStalled](elementlist/onstalled) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onSubmit](elementlist/onsubmit) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

Stream of `submit` events handled by this [Element](element-class).

[onSuspend](elementlist/onsuspend) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onTimeUpdate](elementlist/ontimeupdate) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onTouchCancel](elementlist/ontouchcancel) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchcancel` events handled by this [Element](element-class).

[onTouchEnd](elementlist/ontouchend) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchend` events handled by this [Element](element-class).

[onTouchEnter](elementlist/ontouchenter) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchenter` events handled by this [Element](element-class).

[onTouchLeave](elementlist/ontouchleave) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchleave` events handled by this [Element](element-class).

[onTouchMove](elementlist/ontouchmove) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchmove` events handled by this [Element](element-class).

[onTouchStart](elementlist/ontouchstart) →
[ElementStream](elementstream-class)\<[TouchEvent](touchevent-class)\>

::: {.features}
read-only
:::

Stream of `touchstart` events handled by this [Element](element-class).

[onTransitionEnd](elementlist/ontransitionend) →
[ElementStream](elementstream-class)\<[TransitionEvent](transitionevent-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI), read-only
:::

Stream of `transitionend` events handled by this
[Element](element-class).

[onVolumeChange](elementlist/onvolumechange) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onWaiting](elementlist/onwaiting) →
[ElementStream](elementstream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onWheel](elementlist/onwheel) →
[ElementStream](elementstream-class)\<[WheelEvent](wheelevent-class)\>

::: {.features}
read-only
:::

[paddingEdge](elementlist/paddingedge) → [CssRect](cssrect-class)

::: {.features}
read-only
:::

Access dimensions and position of the first [Element](element-class)\'s
content + padding box in this list.

[reversed](../dart-collection/listmixin/reversed) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
read-only, inherited
:::

An [Iterable](../dart-core/iterable-class) of the objects in this list
in reverse order.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](../dart-collection/listmixin/single) → T

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

[style](elementlist/style) →
[CssStyleDeclarationBase](cssstyledeclarationbase-class)

::: {.features}
read-only
:::

Access the union of all
[CssStyleDeclaration](cssstyledeclaration-class)s that are associated
with an [ElementList](elementlist-class).

Methods {#instance-methods}
-------

[add](../dart-collection/listmixin/add)(T element) → void

::: {.features}
inherited
:::

Adds `value` to the end of this list, extending the length by one.

[addAll](../dart-collection/listmixin/addall)([Iterable](../dart-core/iterable-class)\<T\>
iterable) → void

::: {.features}
inherited
:::

Appends all objects of `iterable` to the end of this list.

[any](../dart-collection/listmixin/any)([bool](../dart-core/bool-class)
test(T element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](../dart-collection/listmixin/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class), T\>

::: {.features}
inherited
:::

An unmodifiable [Map](../dart-core/map-class) view of this list.

[cast](../dart-collection/listmixin/cast)\<R\>() →
[List](../dart-core/list-class)\<R\>

::: {.features}
inherited
:::

Returns a view of this list as a list of `R` instances.

[clear](../dart-collection/listmixin/clear)() → void

::: {.features}
inherited
:::

Removes all objects from this list; the length of the list becomes zero.

[contains](../dart-collection/listmixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](../dart-collection/listmixin/elementat)([int](../dart-core/int-class)
index) → T

::: {.features}
inherited
:::

Returns the `index`th element.

[every](../dart-collection/listmixin/every)([bool](../dart-core/bool-class)
test(T element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-collection/listmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f(T element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](../dart-collection/listmixin/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end, \[T? fill\]) → void

::: {.features}
inherited
:::

Overwrites a range of elements with `fillValue`.

[firstWhere](../dart-collection/listmixin/firstwhere)([bool](../dart-core/bool-class)
test(T element), {T orElse()?}) → T

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-collection/listmixin/fold)\<T\>(T initialValue, T
combine(T previousValue, T element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-collection/listmixin/followedby)([Iterable](../dart-core/iterable-class)\<T\>
other) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-collection/listmixin/foreach)(void action(T element))
→ void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](../dart-collection/listmixin/getrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Creates an [Iterable](../dart-core/iterable-class) that iterates over a
range of elements.

[indexOf](../dart-collection/listmixin/indexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index of `element` in this list.

[indexWhere](../dart-collection/listmixin/indexwhere)([bool](../dart-core/bool-class)
test(T element), \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[insert](../dart-collection/listmixin/insert)([int](../dart-core/int-class)
index, T element) → void

::: {.features}
inherited
:::

Inserts `element` at position `index` in this list.

[insertAll](../dart-collection/listmixin/insertall)([int](../dart-core/int-class)
index, [Iterable](../dart-core/iterable-class)\<T\> iterable) → void

::: {.features}
inherited
:::

Inserts all objects of `iterable` at position `index` in this list.

[join](../dart-collection/listmixin/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastIndexOf](../dart-collection/listmixin/lastindexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index of `element` in this list.

[lastIndexWhere](../dart-collection/listmixin/lastindexwhere)([bool](../dart-core/bool-class)
test(T element), \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](../dart-collection/listmixin/lastwhere)([bool](../dart-core/bool-class)
test(T element), {T orElse()?}) → T

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](../dart-collection/listmixin/map)\<T\>(T f(T element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

The current elements of this iterable modified by `toElement`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](../dart-collection/listmixin/reduce)(T combine(T previousValue,
T element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](../dart-collection/listmixin/remove)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Removes the first occurrence of `value` from this list.

[removeAt](../dart-collection/listmixin/removeat)([int](../dart-core/int-class)
index) → T

::: {.features}
inherited
:::

Removes the object at position `index` from this list.

[removeLast](../dart-collection/listmixin/removelast)() → T

::: {.features}
inherited
:::

Removes and returns the last object in this list.

[removeRange](../dart-collection/listmixin/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
inherited
:::

Removes a range of elements from the list.

[removeWhere](../dart-collection/listmixin/removewhere)([bool](../dart-core/bool-class)
test(T element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that satisfy `test`.

[replaceRange](../dart-collection/listmixin/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<T\> newContents) → void

::: {.features}
inherited
:::

Replaces a range of elements with the elements of `replacements`.

[retainWhere](../dart-collection/listmixin/retainwhere)([bool](../dart-core/bool-class)
test(T element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that fail to satisfy `test`.

[setAll](../dart-collection/listmixin/setall)([int](../dart-core/int-class)
index, [Iterable](../dart-core/iterable-class)\<T\> iterable) → void

::: {.features}
inherited
:::

Overwrites elements with the objects of `iterable`.

[setRange](../dart-collection/listmixin/setrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<T\> iterable,
\[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
inherited
:::

Writes some elements of `iterable` into a range of this list.

[shuffle](../dart-collection/listmixin/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
inherited
:::

Shuffles the elements of this list randomly.

[singleWhere](../dart-collection/listmixin/singlewhere)([bool](../dart-core/bool-class)
test(T element), {T orElse()?}) → T

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-collection/listmixin/skip)([int](../dart-core/int-class)
count) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-collection/listmixin/skipwhile)([bool](../dart-core/bool-class)
test(T element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](../dart-collection/listmixin/sort)(\[[int](../dart-core/int-class)
compare(T a, T b)?\]) → void

::: {.features}
inherited
:::

Sorts this list according to the order specified by the `compare`
function.

[sublist](../dart-collection/listmixin/sublist)([int](../dart-core/int-class)
start, \[[int](../dart-core/int-class)? end\]) →
[List](../dart-core/list-class)\<T\>

::: {.features}
inherited
:::

Returns a new list containing the elements between `start` and `end`.

[take](../dart-collection/listmixin/take)([int](../dart-core/int-class)
count) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-collection/listmixin/takewhile)([bool](../dart-core/bool-class)
test(T element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-collection/listmixin/tolist)({[bool](../dart-core/bool-class)
growable = true}) → [List](../dart-core/list-class)\<T\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-collection/listmixin/toset)() →
[Set](../dart-core/set-class)\<T\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](../dart-collection/listmixin/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[where](../dart-collection/listmixin/where)([bool](../dart-core/bool-class)
test(T element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](../dart-collection/listmixin/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

Operators
---------

[operator
+](../dart-collection/listmixin/operator_plus)([List](../dart-core/list-class)\<T\>
other) → [List](../dart-core/list-class)\<T\>

::: {.features}
inherited
:::

Returns the concatenation of this list and `other`.

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](../dart-core/list/operator_get)([int](../dart-core/int-class)
index) → T

::: {.features}
inherited
:::

The object at the given `index` in the list.

[operator
\[\]=](../dart-core/list/operator_put)([int](../dart-core/int-class)
index, T value) → void

::: {.features}
inherited
:::

Sets the value at the given `index` in the list to `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ElementList-class.html>
:::
