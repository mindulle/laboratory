[dart:html](../dart-html/dart-html-library){._links-link}

EventStreamProvider\<T extends Event\> class
============================================

A factory to expose DOM events as Streams.

Constructors
------------

[EventStreamProvider](eventstreamprovider/eventstreamprovider)([String](../dart-core/string-class)
\_eventType)

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[forElement](eventstreamprovider/forelement)([Element](element-class) e,
{[bool](../dart-core/bool-class) useCapture = false}) →
[ElementStream](elementstream-class)\<T\>

Gets a [Stream](../dart-async/stream-class) for this event type, on the
specified element.

[forTarget](eventstreamprovider/fortarget)([EventTarget](eventtarget-class)?
e, {[bool](../dart-core/bool-class) useCapture = false}) →
[Stream](../dart-async/stream-class)\<T\>

Gets a [Stream](../dart-async/stream-class) for this event type, on the
specified target.

[getEventType](eventstreamprovider/geteventtype)([EventTarget](eventtarget-class)
target) → [String](../dart-core/string-class)

Gets the type of the event which this would listen for on the specified
event target.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

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
<https://api.dart.dev/stable/2.18.5/dart-html/EventStreamProvider-class.html>
:::
