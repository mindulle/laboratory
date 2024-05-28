[dart:web\_audio](../dart-web_audio/dart-web_audio-library){._links-link}

DelayNode class
===============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](../dart-html/eventtarget-class)
    -   [AudioNode](audionode-class)
    -   DelayNode

Annotations

:   -   \@Native(\"DelayNode\")

Constructors
------------

[DelayNode](delaynode/delaynode)([BaseAudioContext](baseaudiocontext-class)
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

[context](audionode/context) →
[BaseAudioContext](baseaudiocontext-class)?

::: {.features}
read-only, inherited
:::

[delayTime](delaynode/delaytime) → [AudioParam](audioparam-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

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
<https://api.dart.dev/stable/2.18.5/dart-web_audio/DelayNode-class.html>
:::
