[dart:html](../dart-html/dart-html-library){._links-link}

PointerEvent class
==================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Event](event-class)
    -   [UIEvent](uievent-class)
    -   [MouseEvent](mouseevent-class)
    -   PointerEvent

Annotations

:   -   \@Native(\"PointerEvent\")

Constructors
------------

[PointerEvent](pointerevent/pointerevent)([String](../dart-core/string-class)
type, \[[Map](../dart-core/map-class)? eventInitDict\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[altKey](mouseevent/altkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[bubbles](event/bubbles) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[button](mouseevent/button) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[buttons](mouseevent/buttons) → [int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

[cancelable](event/cancelable) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[client](mouseevent/client) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only, inherited
:::

[composed](event/composed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[ctrlKey](mouseevent/ctrlkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[currentTarget](event/currenttarget) → [EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
:::

[dataTransfer](mouseevent/datatransfer) →
[DataTransfer](datatransfer-class)

::: {.features}
read-only, inherited
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
read-only, inherited
:::

The nonstandard way to access the element that the mouse comes from in
the case of a `mouseover` event.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[height](pointerevent/height) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[isPrimary](pointerevent/isprimary) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[isTrusted](event/istrusted) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[layer](mouseevent/layer) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only, inherited
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
read-only, inherited
:::

[movement](mouseevent/movement) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX), read-only, inherited
:::

[offset](mouseevent/offset) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only, inherited
:::

The coordinates of the mouse pointer in target node coordinates.

[page](mouseevent/page) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only, inherited
:::

[path](event/path) →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
read-only, inherited
:::

[pointerId](pointerevent/pointerid) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[pointerType](pointerevent/pointertype) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[pressure](pointerevent/pressure) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[region](mouseevent/region) → [String](../dart-core/string-class)?

::: {.features}
read-only, inherited
:::

[relatedTarget](mouseevent/relatedtarget) →
[EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
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
read-only, inherited
:::

[shiftKey](mouseevent/shiftkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[sourceCapabilities](uievent/sourcecapabilities) →
[InputDeviceCapabilities](inputdevicecapabilities-class)?

::: {.features}
read-only, inherited
:::

[tangentialPressure](pointerevent/tangentialpressure) →
[num](../dart-core/num-class)?

::: {.features}
read-only
:::

[target](event/target) → [EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
:::

[tiltX](pointerevent/tiltx) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[tiltY](pointerevent/tilty) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[timeStamp](event/timestamp) → [num](../dart-core/num-class)?

::: {.features}
read-only, inherited
:::

[toElement](mouseevent/toelement){.deprecated} → [Node](node-class)?

::: {.features}
read-only, inherited
:::

The nonstandard way to access the element that the mouse goes to in the
case of a `mouseout` event.

[twist](pointerevent/twist) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[type](event/type) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

[view](uievent/view) → [WindowBase](windowbase-class)?

::: {.features}
read-only, inherited
:::

[width](pointerevent/width) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[composedPath](event/composedpath)() →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
inherited
:::

[getCoalescedEvents](pointerevent/getcoalescedevents)() →
[List](../dart-core/list-class)\<[PointerEvent](pointerevent-class)\>

[getModifierState](mouseevent/getmodifierstate)([String](../dart-core/string-class)
keyArg) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

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

Static Properties
-----------------

[supported](pointerevent/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

PointerEvent used for both touch and mouse. To check if touch is
supported call the property TouchEvent.supported

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PointerEvent-class.html>
:::
