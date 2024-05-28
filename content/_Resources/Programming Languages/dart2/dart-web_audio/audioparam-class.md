[dart:web\_audio](../dart-web_audio/dart-web_audio-library){._links-link}

AudioParam class
================

Annotations

:   -   \@Native(\"AudioParam\")

Properties {#instance-properties}
----------

[defaultValue](audioparam/defaultvalue) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[maxValue](audioparam/maxvalue) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[minValue](audioparam/minvalue) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[value](audioparam/value) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

Methods {#instance-methods}
-------

[cancelAndHoldAtTime](audioparam/cancelandholdattime)([num](../dart-core/num-class)
startTime) → [AudioParam](audioparam-class)

[cancelScheduledValues](audioparam/cancelscheduledvalues)([num](../dart-core/num-class)
startTime) → [AudioParam](audioparam-class)

[exponentialRampToValueAtTime](audioparam/exponentialramptovalueattime)([num](../dart-core/num-class)
value, [num](../dart-core/num-class) time) →
[AudioParam](audioparam-class)

[linearRampToValueAtTime](audioparam/linearramptovalueattime)([num](../dart-core/num-class)
value, [num](../dart-core/num-class) time) →
[AudioParam](audioparam-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setTargetAtTime](audioparam/settargetattime)([num](../dart-core/num-class)
target, [num](../dart-core/num-class) time,
[num](../dart-core/num-class) timeConstant) →
[AudioParam](audioparam-class)

[setValueAtTime](audioparam/setvalueattime)([num](../dart-core/num-class)
value, [num](../dart-core/num-class) time) →
[AudioParam](audioparam-class)

[setValueCurveAtTime](audioparam/setvaluecurveattime)([List](../dart-core/list-class)\<[num](../dart-core/num-class)\>
values, [num](../dart-core/num-class) time,
[num](../dart-core/num-class) duration) → [AudioParam](audioparam-class)

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
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioParam-class.html>
:::
