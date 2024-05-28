[dart:html](../dart-html/dart-html-library){._links-link}

Events class
============

Base class that supports listening for and dispatching browser events.

Normally events are accessed via the Stream getter:

``` {.language-dart data-language="dart"}
element.onMouseOver.listen((e) => print('Mouse over!'));
```

To access bubbling events which are declared on one element, but may
bubble up to another element type (common for MediaElement events):

``` {.language-dart data-language="dart"}
MediaElement.pauseEvent.forTarget(document.body).listen(...);
```

To useCapture on events:

``` {.language-dart data-language="dart"}
Element.keyDownEvent.forTarget(element, useCapture: true).listen(...);
```

Custom events can be declared as:

``` {.language-dart data-language="dart"}
class DataGenerator {
  static EventStreamProvider<Event> dataEvent =
      new EventStreamProvider('data');
}
```

Then listeners should access the event with:

``` {.language-dart data-language="dart"}
DataGenerator.dataEvent.forTarget(element).listen(...);
```

Custom events can also be accessed as:

``` {.language-dart data-language="dart"}
element.on['some_event'].listen(...);
```

This approach is generally discouraged as it loses the event typing and
some DOM events may have multiple platform-dependent event names under
the covers. By using the standard Stream getters you will get the
platform specific event name automatically.

Implementers

:   -   [ElementEvents](elementevents-class)

Constructors
------------

[Events](events/events)([EventTarget](eventtarget-class) \_ptr)

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

[operator \[\]](events/operator_get)([String](../dart-core/string-class)
type) → [Stream](../dart-async/stream-class)\<[Event](event-class)\>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Events-class.html>
:::
