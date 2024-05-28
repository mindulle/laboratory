[dart:developer](../dart-developer/dart-developer-library){._links-link}

Flow class
==========

A class to represent Flow events.

[Flow](flow-class) objects are used to thread flow events between
timeline slices, for example, those created with the
[Timeline](timeline-class) class below. Adding [Flow](flow-class)
objects cause arrows to be drawn between slices in Chrome\'s trace
viewer. The arrows start at e.g [Timeline](timeline-class) events that
are passed a [Flow.begin](flow/begin) object, go through
[Timeline](timeline-class) events that are passed a
[Flow.step](flow/step) object, and end at [Timeline](timeline-class)
events that are passed a [Flow.end](flow/end) object, all having the
same [Flow.id](flow/id). For example:

``` {.language-dart data-language="dart"}
var flow = Flow.begin();
Timeline.timeSync('flow_test', () {
  doSomething();
}, flow: flow);

Timeline.timeSync('flow_test', () {
  doSomething();
}, flow: Flow.step(flow.id));

Timeline.timeSync('flow_test', () {
  doSomething();
}, flow: Flow.end(flow.id));
```

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](flow/id) → [int](../dart-core/int-class)

::: {.features}
final
:::

The flow id of the flow event.

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

Static Methods
--------------

[begin](flow/begin)({[int](../dart-core/int-class)? id}) → [Flow](flow-class)
:   A \"begin\" Flow event.

[end](flow/end)([int](../dart-core/int-class) id) → [Flow](flow-class)
:   An \"end\" Flow event.

[step](flow/step)([int](../dart-core/int-class) id) → [Flow](flow-class)
:   A \"step\" Flow event.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Flow-class.html>
:::
