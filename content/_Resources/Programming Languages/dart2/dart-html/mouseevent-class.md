[dart:html](../dart-html/dart-html-library){._links-link}

MouseEvent class
================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Event](event-class)
    -   [UIEvent](uievent-class)
    -   MouseEvent

Implementers

:   -   [PointerEvent](pointerevent-class)
    -   [WheelEvent](wheelevent-class)

Annotations

:   -   \@Native(\"MouseEvent,DragEvent\")

Constructors
------------

[MouseEvent](mouseevent/mouseevent)([String](../dart-core/string-class)
type, {[Window](window-class)? view, [int](../dart-core/int-class)
detail = 0, [int](../dart-core/int-class) screenX = 0,
[int](../dart-core/int-class) screenY = 0, [int](../dart-core/int-class)
clientX = 0, [int](../dart-core/int-class) clientY = 0,
[int](../dart-core/int-class) button = 0,
[bool](../dart-core/bool-class) canBubble = true,
[bool](../dart-core/bool-class) cancelable = true,
[bool](../dart-core/bool-class) ctrlKey = false,
[bool](../dart-core/bool-class) altKey = false,
[bool](../dart-core/bool-class) shiftKey = false,
[bool](../dart-core/bool-class) metaKey = false,
[EventTarget](eventtarget-class)? relatedTarget})

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[altKey](mouseevent/altkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[bubbles](event/bubbles) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[button](mouseevent/button) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[buttons](mouseevent/buttons) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[cancelable](event/cancelable) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[client](mouseevent/client) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[composed](event/composed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[ctrlKey](mouseevent/ctrlkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[currentTarget](event/currenttarget) → [EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
:::

[dataTransfer](mouseevent/datatransfer) →
[DataTransfer](datatransfer-class)

::: {.features}
read-only
:::

[defaultPrevented](event/defaultprevented) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[detail](uievent/detail) → [int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

[eventPhase](event/eventphase) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[fromElement](mouseevent/fromelement){.deprecated} → [Node](node-class)?

::: {.features}
read-only
:::

The nonstandard way to access the element that the mouse comes from in
the case of a `mouseover` event.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isTrusted](event/istrusted) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[layer](mouseevent/layer) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[matchingTarget](event/matchingtarget) → [Element](element-class)

::: {.features}
read-only, inherited
:::

A pointer to the element whose CSS selector matched within which an
event was fired. If this Event was not associated with any Event
delegation, accessing this value will throw an
[UnsupportedError](../dart-core/unsupportederror-class).

[metaKey](mouseevent/metakey) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[movement](mouseevent/movement) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX), read-only
:::

[offset](mouseevent/offset) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

The coordinates of the mouse pointer in target node coordinates.

[page](mouseevent/page) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[path](event/path) →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
read-only, inherited
:::

[region](mouseevent/region) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[relatedTarget](mouseevent/relatedtarget) →
[EventTarget](eventtarget-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[screen](mouseevent/screen) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[shiftKey](mouseevent/shiftkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[sourceCapabilities](uievent/sourcecapabilities) →
[InputDeviceCapabilities](inputdevicecapabilities-class)?

::: {.features}
read-only, inherited
:::

[target](event/target) → [EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
:::

[timeStamp](event/timestamp) → [num](../dart-core/num-class)?

::: {.features}
read-only, inherited
:::

[toElement](mouseevent/toelement){.deprecated} → [Node](node-class)?

::: {.features}
read-only
:::

The nonstandard way to access the element that the mouse goes to in the
case of a `mouseout` event.

[type](event/type) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

[view](uievent/view) → [WindowBase](windowbase-class)?

::: {.features}
read-only, inherited
:::

Methods {#instance-methods}
-------

[composedPath](event/composedpath)() →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
inherited
:::

[getModifierState](mouseevent/getmodifierstate)([String](../dart-core/string-class)
keyArg) → [bool](../dart-core/bool-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[preventDefault](event/preventdefault)() → void

::: {.features}
inherited
:::

[stopImmediatePropagation](event/stopimmediatepropagation)() → void

::: {.features}
inherited
:::

[stopPropagation](event/stoppropagation)() → void

::: {.features}
inherited
:::

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
<https://api.dart.dev/stable/2.18.5/dart-html/MouseEvent-class.html>
:::
