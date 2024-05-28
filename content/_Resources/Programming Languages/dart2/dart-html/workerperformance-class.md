[dart:html](../dart-html/dart-html-library){._links-link}

WorkerPerformance class
=======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   WorkerPerformance

Annotations

:   -   \@Native(\"WorkerPerformance\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[memory](workerperformance/memory) → [MemoryInfo](memoryinfo-class)?

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

[timeOrigin](workerperformance/timeorigin) →
[num](../dart-core/num-class)?

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

[clearMarks](workerperformance/clearmarks)([String](../dart-core/string-class)?
markName) → void

[clearMeasures](workerperformance/clearmeasures)([String](../dart-core/string-class)?
measureName) → void

[clearResourceTimings](workerperformance/clearresourcetimings)() → void

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getEntries](workerperformance/getentries)() →
[List](../dart-core/list-class)\<[PerformanceEntry](performanceentry-class)\>

[getEntriesByName](workerperformance/getentriesbyname)([String](../dart-core/string-class)
name, [String](../dart-core/string-class)? entryType) →
[List](../dart-core/list-class)\<[PerformanceEntry](performanceentry-class)\>

[getEntriesByType](workerperformance/getentriesbytype)([String](../dart-core/string-class)
entryType) →
[List](../dart-core/list-class)\<[PerformanceEntry](performanceentry-class)\>

[mark](workerperformance/mark)([String](../dart-core/string-class)
markName) → void

[measure](workerperformance/measure)([String](../dart-core/string-class)
measureName, [String](../dart-core/string-class)? startMark,
[String](../dart-core/string-class)? endMark) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[now](workerperformance/now)() → [double](../dart-core/double-class)

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[setResourceTimingBufferSize](workerperformance/setresourcetimingbuffersize)([int](../dart-core/int-class)
maxSize) → void

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
<https://api.dart.dev/stable/2.18.5/dart-html/WorkerPerformance-class.html>
:::
