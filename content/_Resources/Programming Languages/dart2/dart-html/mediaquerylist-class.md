[dart:html](../dart-html/dart-html-library){._links-link}

MediaQueryList class
====================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   MediaQueryList

Annotations

:   -   \@Unstable()
    -   \@Native(\"MediaQueryList\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[matches](mediaquerylist/matches) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

[media](mediaquerylist/media) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[onChange](mediaquerylist/onchange) →
[Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[addListener](mediaquerylist/addlistener)([EventListener](eventlistener)?
listener) → void

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

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[removeListener](mediaquerylist/removelistener)([EventListener](eventlistener)?
listener) → void

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

Constants
---------

[changeEvent](mediaquerylist/changeevent-constant) → const [EventStreamProvider](eventstreamprovider-class)\<[Event](event-class)\>

:   <div>

    `const EventStreamProvider<Event>('change')`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaQueryList-class.html>
:::
