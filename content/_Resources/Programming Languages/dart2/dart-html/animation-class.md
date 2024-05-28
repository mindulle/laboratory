[dart:html](../dart-html/dart-html-library){._links-link}

Animation class
===============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   Animation

Annotations

:   -   \@Native(\"Animation\")

Constructors
------------

[Animation](animation/animation)(\[[AnimationEffectReadOnly](animationeffectreadonly-class)?
effect, [AnimationTimeline](animationtimeline-class)? timeline\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[currentTime](animation/currenttime) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[effect](animation/effect) ↔
[AnimationEffectReadOnly](animationeffectreadonly-class)?

::: {.features}
read / write
:::

[finished](animation/finished) →
[Future](../dart-async/future-class)\<[Animation](animation-class)\>

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](animation/id) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onCancel](animation/oncancel) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[onFinish](animation/onfinish) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[playbackRate](animation/playbackrate) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[playState](animation/playstate) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[ready](animation/ready) →
[Future](../dart-async/future-class)\<[Animation](animation-class)\>

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[startTime](animation/starttime) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[timeline](animation/timeline) →
[AnimationTimeline](animationtimeline-class)?

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

[cancel](animation/cancel)() → void

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[finish](animation/finish)() → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pause](animation/pause)() → void

[play](animation/play)() → void

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[reverse](animation/reverse)() → void

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

[supported](animation/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Constants
---------

[cancelEvent](animation/cancelevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('cancel')`

    </div>

[finishEvent](animation/finishevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('finish')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Animation-class.html>
:::
