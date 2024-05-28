dart:developer library
======================

Interact with developer tools such as the debugger and inspector.

This library is platform dependent and has separate implementations for
both web and the Dart VM. A specific platform may not support all
operations.

To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:developer';
```

Classes
-------

[Counter](counter-class)
:   A changing value. Initial value is 0.0.

[Flow](flow-class)
:   A class to represent Flow events.

[Gauge](gauge-class)
:   A measured value with a min and max. Initial value is min. Value
    will be clamped to the interval `[min, max]`.

[Metric](metric-class)
:   Abstract [Metric](metric-class) class. Metric names must be unique,
    are hierarchical, and use periods as separators. For example,
    \'a.b.c\'. Uniqueness is only enforced when a Metric is registered.
    The name of a metric cannot contain the slash (\'/\') character.

[Metrics](metrics-class)\
[Service](service-class)
:   Access information about the service protocol and control the web
    server that provides access to the services provided by the Dart VM
    for debugging and inspecting Dart programs.

[ServiceExtensionResponse](serviceextensionresponse-class)
:   A response to a service protocol extension RPC.

[ServiceProtocolInfo](serviceprotocolinfo-class)
:   Service protocol is the protocol that a client like the Observatory
    could use to access the services provided by the Dart VM for
    debugging and inspecting Dart programs. This class encapsulates the
    version number and Uri for accessing this service.

[Timeline](timeline-class)
:   Add to the timeline.

[TimelineTask](timelinetask-class)
:   An asynchronous task on the timeline. An asynchronous task can have
    many (nested) synchronous operations. Synchronous operations can
    live longer than the current isolate event. To pass a
    [TimelineTask](timelinetask-class) to another isolate, you must
    first call [pass](timelinetask/pass) to get the task id and then
    construct a new [TimelineTask](timelinetask-class) in the other
    isolate.

[UserTag](usertag-class)
:   A UserTag can be used to group samples in the [DevTools CPU
    profiler](https://flutter.dev/docs/development/tools/devtools/cpu-profiler).

Properties
----------

[extensionStreamHasListener](extensionstreamhaslistener) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the \"Extension\" stream currently has at least one listener.

Functions
---------

[debugger](debugger)({[bool](../dart-core/bool-class) when = true, [String](../dart-core/string-class)? message}) → [bool](../dart-core/bool-class)
:   If `when` is true, stop the program as if a breakpoint were hit at
    the following statement.

[getCurrentTag](getcurrenttag)() → [UserTag](usertag-class)
:   Returns the current [UserTag](usertag-class) for the isolate.

[inspect](inspect)([Object](../dart-core/object-class)? object) → [Object](../dart-core/object-class)?
:   Send a reference to `object` to any attached debuggers.

[log](log)([String](../dart-core/string-class) message, {[DateTime](../dart-core/datetime-class)? time, [int](../dart-core/int-class)? sequenceNumber, [int](../dart-core/int-class) level = 0, [String](../dart-core/string-class) name = \'\', [Zone](../dart-async/zone-class)? zone, [Object](../dart-core/object-class)? error, [StackTrace](../dart-core/stacktrace-class)? stackTrace}) → void
:   Emit a log event.

[postEvent](postevent)([String](../dart-core/string-class) eventKind, [Map](../dart-core/map-class) eventData) → void
:   Post an event of `eventKind` with payload of `eventData` to the
    \"Extension\" event stream.

[registerExtension](registerextension)([String](../dart-core/string-class) method, [ServiceExtensionHandler](serviceextensionhandler) handler) → void
:   Register a [ServiceExtensionHandler](serviceextensionhandler) that
    will be invoked in this isolate for `method`. *NOTE*: Service
    protocol extensions must be registered in each isolate.

Typedefs
--------

[ServiceExtensionHandler](serviceextensionhandler) = [Future](../dart-async/future-class)\<[ServiceExtensionResponse](serviceextensionresponse-class)\> Function([String](../dart-core/string-class) method, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\> parameters)
:   A service protocol extension handler. Registered with
    [registerExtension](registerextension).

[TimelineAsyncFunction](timelineasyncfunction) = [Future](../dart-async/future-class) Function()\
[TimelineSyncFunction](timelinesyncfunction)\<T\> = T Function()
:   A typedef for the function argument to
    [Timeline.timeSync](timeline/timesync).

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/dart-developer-library.html>
:::
