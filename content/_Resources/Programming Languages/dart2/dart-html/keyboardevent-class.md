[dart:html](../dart-html/dart-html-library){._links-link}

KeyboardEvent class
===================

An event that describes user interaction with the keyboard.

The [type](event/type) of the event identifies what kind of interaction
occurred.

See also:

-   [KeyboardEvent](https://developer.mozilla.org/en/DOM/KeyboardEvent)
    at MDN.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Event](event-class)
    -   [UIEvent](uievent-class)
    -   KeyboardEvent

Implementers

:   -   [KeyEvent](keyevent-class)

Annotations

:   -   \@Native(\"KeyboardEvent\")

Constructors
------------

[KeyboardEvent](keyboardevent/keyboardevent)([String](../dart-core/string-class)
type, {[Window](window-class)? view, [bool](../dart-core/bool-class)
canBubble = true, [bool](../dart-core/bool-class) cancelable = true,
[int](../dart-core/int-class)? location, [int](../dart-core/int-class)?
keyLocation, [bool](../dart-core/bool-class) ctrlKey = false,
[bool](../dart-core/bool-class) altKey = false,
[bool](../dart-core/bool-class) shiftKey = false,
[bool](../dart-core/bool-class) metaKey = false})

::: {.constructor-modifier .features}
factory
:::

Programmatically create a KeyboardEvent.

Properties {#instance-properties}
----------

[altKey](keyboardevent/altkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[bubbles](event/bubbles) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[cancelable](event/cancelable) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[charCode](keyboardevent/charcode) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[code](keyboardevent/code) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[composed](event/composed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[ctrlKey](keyboardevent/ctrlkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[currentTarget](event/currenttarget) → [EventTarget](eventtarget-class)?

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

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isComposing](keyboardevent/iscomposing) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[isTrusted](event/istrusted) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[key](keyboardevent/key) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[keyCode](keyboardevent/keycode) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

[location](keyboardevent/location) → [int](../dart-core/int-class)

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

[metaKey](keyboardevent/metakey) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[path](event/path) →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
read-only, inherited
:::

[repeat](keyboardevent/repeat) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[shiftKey](keyboardevent/shiftkey) → [bool](../dart-core/bool-class)

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

[type](event/type) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

[view](uievent/view) → [WindowBase](windowbase-class)?

::: {.features}
read-only, inherited
:::

[which](keyboardevent/which) → [int](../dart-core/int-class)?

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

[getModifierState](keyboardevent/getmodifierstate)([String](../dart-core/string-class)
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

Constants
---------

[DOM\_KEY\_LOCATION\_LEFT](keyboardevent/dom_key_location_left-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x01`

    </div>

[DOM\_KEY\_LOCATION\_NUMPAD](keyboardevent/dom_key_location_numpad-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x03`

    </div>

[DOM\_KEY\_LOCATION\_RIGHT](keyboardevent/dom_key_location_right-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x02`

    </div>

[DOM\_KEY\_LOCATION\_STANDARD](keyboardevent/dom_key_location_standard-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x00`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyboardEvent-class.html>
:::
