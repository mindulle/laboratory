[dart:html](../dart-html/dart-html-library){._links-link}

OrientationSensor class
=======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   [Sensor](sensor-class)
    -   OrientationSensor

Implementers

:   -   [AbsoluteOrientationSensor](absoluteorientationsensor-class)
    -   [RelativeOrientationSensor](relativeorientationsensor-class)

Annotations

:   -   \@Native(\"OrientationSensor\")

Properties {#instance-properties}
----------

[activated](sensor/activated) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[hasReading](sensor/hasreading) → [bool](../dart-core/bool-class)?

::: {.features}
read-only, inherited
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onError](sensor/onerror) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only, inherited
:::

[quaternion](orientationsensor/quaternion) →
[List](../dart-core/list-class)\<[num](../dart-core/num-class)\>?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[timestamp](sensor/timestamp) → [num](../dart-core/num-class)?

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

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[populateMatrix](orientationsensor/populatematrix)([Object](../dart-core/object-class)
targetBuffer) → void

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[start](sensor/start)() → void

::: {.features}
inherited
:::

[stop](sensor/stop)() → void

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
<https://api.dart.dev/stable/2.18.5/dart-html/OrientationSensor-class.html>
:::
