[dart:developer](../dart-developer/dart-developer-library){._links-link}

TimelineTask class
==================

An asynchronous task on the timeline. An asynchronous task can have many
(nested) synchronous operations. Synchronous operations can live longer
than the current isolate event. To pass a
[TimelineTask](timelinetask-class) to another isolate, you must first
call [pass](timelinetask/pass) to get the task id and then construct a
new [TimelineTask](timelinetask-class) in the other isolate.

Constructors
------------

[TimelineTask](timelinetask/timelinetask)({[TimelineTask](timelinetask-class)? parent, [String](../dart-core/string-class)? filterKey})
:   Create a task. The task ID will be set by the system.

[TimelineTask.withTaskId](timelinetask/timelinetask.withtaskid)([int](../dart-core/int-class) taskId, {[String](../dart-core/string-class)? filterKey})
:   Create a task with an explicit `taskId`. This is useful if you are
    passing a task from one isolate to another.

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

[finish](timelinetask/finish)({[Map](../dart-core/map-class)?
arguments}) → void

Finish the last synchronous operation that was started. Optionally takes
a [Map](../dart-core/map-class) of `arguments`.

[instant](timelinetask/instant)([String](../dart-core/string-class)
name, {[Map](../dart-core/map-class)? arguments}) → void

Emit an instant event for this task. Optionally takes a
[Map](../dart-core/map-class) of `arguments`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pass](timelinetask/pass)() → [int](../dart-core/int-class)

Retrieve the [TimelineTask](timelinetask-class)\'s task id. Will throw
an exception if the stack is not empty.

[start](timelinetask/start)([String](../dart-core/string-class) name,
{[Map](../dart-core/map-class)? arguments}) → void

Start a synchronous operation within this task named `name`. Optionally
takes a [Map](../dart-core/map-class) of `arguments`.

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
<https://api.dart.dev/stable/2.18.5/dart-developer/TimelineTask-class.html>
:::
