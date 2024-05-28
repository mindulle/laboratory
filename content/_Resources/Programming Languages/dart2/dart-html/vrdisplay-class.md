[dart:html](../dart-html/dart-html-library){._links-link}

VRDisplay class
===============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   VRDisplay

Annotations

:   -   \@Native(\"VRDisplay\")

Properties {#instance-properties}
----------

[capabilities](vrdisplay/capabilities) →
[VRDisplayCapabilities](vrdisplaycapabilities-class)?

::: {.features}
read-only
:::

[depthFar](vrdisplay/depthfar) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[depthNear](vrdisplay/depthnear) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[displayId](vrdisplay/displayid) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

[displayName](vrdisplay/displayname) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isPresenting](vrdisplay/ispresenting) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[stageParameters](vrdisplay/stageparameters) →
[VRStageParameters](vrstageparameters-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[cancelAnimationFrame](vrdisplay/cancelanimationframe)([int](../dart-core/int-class)
handle) → void

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[exitPresent](vrdisplay/exitpresent)() →
[Future](../dart-async/future-class)

[getEyeParameters](vrdisplay/geteyeparameters)([String](../dart-core/string-class)
whichEye) → [VREyeParameters](vreyeparameters-class)

[getFrameData](vrdisplay/getframedata)([VRFrameData](vrframedata-class)
frameData) → [bool](../dart-core/bool-class)

[getLayers](vrdisplay/getlayers)() →
[List](../dart-core/list-class)\<[Map](../dart-core/map-class)\>

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[requestAnimationFrame](vrdisplay/requestanimationframe)([FrameRequestCallback](framerequestcallback)
callback) → [int](../dart-core/int-class)

[requestPresent](vrdisplay/requestpresent)([List](../dart-core/list-class)\<[Map](../dart-core/map-class)\>
layers) → [Future](../dart-async/future-class)

[submitFrame](vrdisplay/submitframe)() → void

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
<https://api.dart.dev/stable/2.18.5/dart-html/VRDisplay-class.html>
:::
