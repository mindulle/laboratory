[dart:html](../dart-html/dart-html-library){._links-link}

KeyEvent class
==============

A custom KeyboardEvent that attempts to eliminate cross-browser
inconsistencies, and also provide both keyCode and charCode information
for all key events (when such information can be determined).

KeyEvent tries to provide a higher level, more polished keyboard event
information on top of the \"raw\" [KeyboardEvent](keyboardevent-class).

The mechanics of using KeyEvents is a little different from the
underlying [KeyboardEvent](keyboardevent-class). To use KeyEvents, you
need to create a stream and then add KeyEvents to the stream, rather
than using the [EventTarget.dispatchEvent](eventtarget/dispatchevent).
Here\'s an example usage:

``` {.language-dart data-language="dart"}
// Initialize a stream for the KeyEvents:
var stream = KeyEvent.keyPressEvent.forTarget(document.body);
// Start listening to the stream of KeyEvents.
stream.listen((keyEvent) =>
    window.console.log('KeyPress event detected ${keyEvent.charCode}'));
...
// Add a new KeyEvent of someone pressing the 'A' key to the stream so
// listeners can know a KeyEvent happened.
stream.add(new KeyEvent('keypress', keyCode: 65, charCode: 97));
```

This class is very much a work in progress, and we\'d love to get
information on how we can make this class work with as many
international keyboards as possible. Bugs welcome!

Implemented types

:   -   [KeyboardEvent](keyboardevent-class)

Constructors
------------

[KeyEvent](keyevent/keyevent)([String](../dart-core/string-class) type,
{[Window](window-class)? view, [bool](../dart-core/bool-class) canBubble
= true, [bool](../dart-core/bool-class) cancelable = true,
[int](../dart-core/int-class) keyCode = 0, [int](../dart-core/int-class)
charCode = 0, [int](../dart-core/int-class) location = 1,
[bool](../dart-core/bool-class) ctrlKey = false,
[bool](../dart-core/bool-class) altKey = false,
[bool](../dart-core/bool-class) shiftKey = false,
[bool](../dart-core/bool-class) metaKey = false,
[EventTarget](eventtarget-class)? currentTarget})

::: {.constructor-modifier .features}
factory
:::

Programmatically create a new KeyEvent (and KeyboardEvent).

[KeyEvent.wrap](keyevent/keyevent.wrap)([KeyboardEvent](keyboardevent-class)
parent)

Construct a KeyEvent with `parent` as the event we\'re emulating.

Properties {#instance-properties}
----------

[altKey](keyevent/altkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Calculated value of whether the alt key is pressed is for this event.

[bubbles](keyevent/bubbles) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[cancelable](keyevent/cancelable) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[charCode](keyevent/charcode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Calculated value of what the estimated charCode is for this event.

[code](keyevent/code) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

[composed](keyevent/composed) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[ctrlKey](keyevent/ctrlkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

True if the ctrl key is pressed during this event.

[currentTarget](keyevent/currenttarget) →
[EventTarget](eventtarget-class)?

::: {.features}
read-only
:::

The currently registered target for this event.

[defaultPrevented](keyevent/defaultprevented) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[detail](keyevent/detail) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

[eventPhase](keyevent/eventphase) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isComposed](keyevent/iscomposed) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[isComposing](keyevent/iscomposing) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

[isTrusted](keyevent/istrusted) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

[key](keyevent/key) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

[keyCode](keyevent/keycode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Calculated value of what the estimated keyCode is for this event.

[location](keyevent/location) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Accessor to the part of the keyboard that the key was pressed from (one
of KeyLocation.STANDARD, KeyLocation.RIGHT, KeyLocation.LEFT,
KeyLocation.NUMPAD, KeyLocation.MOBILE, KeyLocation.JOYSTICK).

[matchingTarget](keyevent/matchingtarget) → [Element](element-class)

::: {.features}
read-only, inherited
:::

A pointer to the element whose CSS selector matched within which an
event was fired. If this Event was not associated with any Event
delegation, accessing this value will throw an
[UnsupportedError](../dart-core/unsupportederror-class).

[metaKey](keyevent/metakey) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

True if the Meta (or Mac command) key is pressed during this event.

[path](keyevent/path) →
[List](../dart-core/list-class)\<[Node](node-class)\>

::: {.features}
read-only, inherited
:::

This event\'s path, taking into account shadow DOM.

[repeat](keyevent/repeat) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[shiftKey](keyevent/shiftkey) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

True if the shift key was pressed during this event.

[sourceCapabilities](keyevent/sourcecapabilities) →
[InputDeviceCapabilities](inputdevicecapabilities-class)?

::: {.features}
read-only, override
:::

[target](keyevent/target) → [EventTarget](eventtarget-class)?

::: {.features}
read-only, inherited
:::

[timeStamp](keyevent/timestamp) → [double](../dart-core/double-class)

::: {.features}
read-only, inherited
:::

[type](keyevent/type) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

[view](keyevent/view) → [WindowBase](windowbase-class)?

::: {.features}
read-only, override
:::

[which](keyevent/which) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Calculated value of what the estimated keyCode is for this event.

[wrapped](keyevent/wrapped) → [Event](event-class)

::: {.features}
final, inherited
:::

Methods {#instance-methods}
-------

[composedPath](keyevent/composedpath)() →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
inherited
:::

[getModifierState](keyevent/getmodifierstate)([String](../dart-core/string-class)
keyArgument) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[preventDefault](keyevent/preventdefault)() → void

::: {.features}
inherited
:::

[stopImmediatePropagation](keyevent/stopimmediatepropagation)() → void

::: {.features}
inherited
:::

[stopPropagation](keyevent/stoppropagation)() → void

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

[canUseDispatchEvent](keyevent/canusedispatchevent) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[keyDownEvent](keyevent/keydownevent) ↔
[EventStreamProvider](eventstreamprovider-class)\<[KeyEvent](keyevent-class)\>

::: {.features}
read / write
:::

Accessor to provide a stream of KeyEvents on the desired target.

[keyPressEvent](keyevent/keypressevent) ↔
[EventStreamProvider](eventstreamprovider-class)\<[KeyEvent](keyevent-class)\>

::: {.features}
read / write
:::

Accessor to provide a stream of KeyEvents on the desired target.

[keyUpEvent](keyevent/keyupevent) ↔
[EventStreamProvider](eventstreamprovider-class)\<[KeyEvent](keyevent-class)\>

::: {.features}
read / write
:::

Accessor to provide a stream of KeyEvents on the desired target.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyEvent-class.html>
:::
