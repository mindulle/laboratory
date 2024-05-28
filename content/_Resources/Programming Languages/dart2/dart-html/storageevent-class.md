[dart:html](../dart-html/dart-html-library){._links-link}

StorageEvent class
==================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Event](event-class)
    -   StorageEvent

Annotations

:   -   \@Unstable()
    -   \@Native(\"StorageEvent\")

Constructors
------------

[StorageEvent](storageevent/storageevent)([String](../dart-core/string-class)
type, {[bool](../dart-core/bool-class) canBubble = false,
[bool](../dart-core/bool-class) cancelable = false,
[String](../dart-core/string-class)? key,
[String](../dart-core/string-class)? oldValue,
[String](../dart-core/string-class)? newValue,
[String](../dart-core/string-class)? url, [Storage](storage-class)?
storageArea})

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

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

[key](storageevent/key) → [String](../dart-core/string-class)?

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

[newValue](storageevent/newvalue) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[oldValue](storageevent/oldvalue) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

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

[storageArea](storageevent/storagearea) → [Storage](storage-class)?

::: {.features}
read-only
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

[url](storageevent/url) → [String](../dart-core/string-class)?

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
<https://api.dart.dev/stable/2.18.5/dart-html/StorageEvent-class.html>
:::
