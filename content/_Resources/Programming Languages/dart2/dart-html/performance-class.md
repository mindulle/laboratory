[dart:html](../dart-html/dart-html-library){._links-link}

Performance class
=================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   Performance

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX)
    -   \@SupportedBrowser(SupportedBrowser.IE)
    -   \@Native(\"Performance\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[memory](performance/memory) → [MemoryInfo](memoryinfo-class)?

::: {.features}
read-only
:::

[navigation](performance/navigation) →
[PerformanceNavigation](performancenavigation-class)

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

[timeOrigin](performance/timeorigin) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[timing](performance/timing) →
[PerformanceTiming](performancetiming-class)

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

[clearMarks](performance/clearmarks)([String](../dart-core/string-class)?
markName) → void

[clearMeasures](performance/clearmeasures)([String](../dart-core/string-class)?
measureName) → void

[clearResourceTimings](performance/clearresourcetimings)() → void

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getEntries](performance/getentries)() →
[List](../dart-core/list-class)\<[PerformanceEntry](performanceentry-class)\>

[getEntriesByName](performance/getentriesbyname)([String](../dart-core/string-class)
name, [String](../dart-core/string-class)? entryType) →
[List](../dart-core/list-class)\<[PerformanceEntry](performanceentry-class)\>

[getEntriesByType](performance/getentriesbytype)([String](../dart-core/string-class)
entryType) →
[List](../dart-core/list-class)\<[PerformanceEntry](performanceentry-class)\>

[mark](performance/mark)([String](../dart-core/string-class) markName,
\[[Map](../dart-core/map-class)? markOptions\]) →
[PerformanceEntry](performanceentry-class)?

[measure](performance/measure)([String](../dart-core/string-class)
measureName, \[dynamic measureOptions\_OR\_startMark,
[String](../dart-core/string-class)? endMark\]) →
[PerformanceMeasure](performancemeasure-class)?

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[now](performance/now)() → [double](../dart-core/double-class)

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[setResourceTimingBufferSize](performance/setresourcetimingbuffersize)([int](../dart-core/int-class)
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

Static Properties
-----------------

[supported](performance/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Performance-class.html>
:::
