[dart:web\_audio](../dart-web_audio/dart-web_audio-library){._links-link}

PannerNode class
================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](../dart-html/eventtarget-class)
    -   [AudioNode](audionode-class)
    -   PannerNode

Annotations

:   -   \@Native(\"PannerNode,AudioPannerNode,webkitAudioPannerNode\")

Constructors
------------

[PannerNode](pannernode/pannernode)([BaseAudioContext](baseaudiocontext-class)
context, \[[Map](../dart-core/map-class)? options\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[channelCount](audionode/channelcount) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write, inherited
:::

[channelCountMode](audionode/channelcountmode) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[channelInterpretation](audionode/channelinterpretation) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write, inherited
:::

[coneInnerAngle](pannernode/coneinnerangle) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[coneOuterAngle](pannernode/coneouterangle) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[coneOuterGain](pannernode/coneoutergain) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[context](audionode/context) →
[BaseAudioContext](baseaudiocontext-class)?

::: {.features}
read-only, inherited
:::

[distanceModel](pannernode/distancemodel) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[maxDistance](pannernode/maxdistance) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[numberOfInputs](audionode/numberofinputs) →
[int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

[numberOfOutputs](audionode/numberofoutputs) →
[int](../dart-core/int-class)?

::: {.features}
read-only, inherited
:::

[on](../dart-html/eventtarget/on) → [Events](../dart-html/events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[orientationX](pannernode/orientationx) →
[AudioParam](audioparam-class)?

::: {.features}
read-only
:::

[orientationY](pannernode/orientationy) →
[AudioParam](audioparam-class)?

::: {.features}
read-only
:::

[orientationZ](pannernode/orientationz) →
[AudioParam](audioparam-class)?

::: {.features}
read-only
:::

[panningModel](pannernode/panningmodel) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

[positionX](pannernode/positionx) → [AudioParam](audioparam-class)?

::: {.features}
read-only
:::

[positionY](pannernode/positiony) → [AudioParam](audioparam-class)?

::: {.features}
read-only
:::

[positionZ](pannernode/positionz) → [AudioParam](audioparam-class)?

::: {.features}
read-only
:::

[refDistance](pannernode/refdistance) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[rolloffFactor](pannernode/rollofffactor) ↔
[num](../dart-core/num-class)?

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[addEventListener](../dart-html/eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](../dart-html/eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[connectNode](audionode/connectnode)([AudioNode](audionode-class)
destination, \[[int](../dart-core/int-class) output = 0,
[int](../dart-core/int-class) input = 0\]) → void

::: {.features}
inherited
:::

[connectParam](audionode/connectparam)([AudioParam](audioparam-class)
destination, \[[int](../dart-core/int-class) output = 0\]) → void

::: {.features}
inherited
:::

[disconnect](audionode/disconnect)(\[dynamic destination\_OR\_output,
[int](../dart-core/int-class)? output, [int](../dart-core/int-class)?
input\]) → void

::: {.features}
inherited
:::

[dispatchEvent](../dart-html/eventtarget/dispatchevent)([Event](../dart-html/event-class)
event) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](../dart-html/eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](../dart-html/eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[setOrientation](pannernode/setorientation)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y, [num](../dart-core/num-class) z) →
void

[setPosition](pannernode/setposition)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) z) → void

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
<https://api.dart.dev/stable/2.18.5/dart-web_audio/PannerNode-class.html>
:::
