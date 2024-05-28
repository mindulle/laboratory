[dart:html](../dart-html/dart-html-library){._links-link}

AnimationEvent class
====================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Event](event-class)
    -   AnimationEvent

Annotations

:   -   \@Native(\"AnimationEvent\")

Constructors
------------

[AnimationEvent](animationevent/animationevent)([String](../dart-core/string-class)
type, \[[Map](../dart-core/map-class)? eventInitDict\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[animationName](animationevent/animationname) →
[String](../dart-core/string-class)?

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

[composed](event/composed) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
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

[elapsedTime](animationevent/elapsedtime) →
[num](../dart-core/num-class)?

::: {.features}
read-only
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

[isTrusted](event/istrusted) → [bool](../dart-core/bool-class)?

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

[path](event/path) →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

::: {.features}
read-only, inherited
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

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

Methods {#instance-methods}
-------

[composedPath](event/composedpath)() →
[List](../dart-core/list-class)\<[EventTarget](eventtarget-class)\>

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/AnimationEvent-class.html>
:::
