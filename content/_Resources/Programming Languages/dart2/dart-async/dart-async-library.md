dart:async library
==================

Support for asynchronous programming, with classes such as Future and
Stream.

[Future](future-class)s and [Stream](stream-class)s are the fundamental
building blocks of asynchronous programming in Dart. They are supported
directly in the language through `async` and `async*` functions, and are
available to all libraries through the `dart:core` library.

This library provides further tools for creating, consuming and
transforming futures and streams, as well as direct access to other
asynchronous primitives like [Timer](timer-class),
[scheduleMicrotask](schedulemicrotask) and [Zone](zone-class).

To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:async';
```

Future
------

A Future object represents a computation whose return value might not
yet be available. The Future returns the value of the computation when
it completes at some time in the future. Futures are often used for
potentially lengthy computations such as I/O and interaction with users.

Many methods in the Dart libraries return `Future`s when performing
tasks. For example, when binding an `HttpServer` to a host and port, the
`bind()` method returns a Future.

``` {.language-dart data-language="dart"}
HttpServer.bind('127.0.0.1', 4444)
     .then((server) => print('${server.isBroadcast}'))
     .catchError(print);
```

[Future.then](future/then) registers a callback function that runs when
the Future\'s operation, in this case the `bind()` method, completes
successfully. The value returned by the operation is passed into the
callback function. In this example, the `bind()` method returns the
HttpServer object. The callback function prints one of its properties.
[Future.catchError](future/catcherror) registers a callback function
that runs if an error occurs within the Future.

Stream
------

A Stream provides an asynchronous sequence of data. Examples of data
sequences include individual events, like mouse clicks, or sequential
chunks of larger data, like multiple byte lists with the contents of a
file such as mouse clicks, and a stream of byte lists read from a file.
The following example opens a file for reading.
[Stream.listen](stream/listen) registers callback functions that run
each time more data is available, an error has occurred, or the stream
has finished. Further functionality is provided on
[Stream](stream-class), implemented by calling
[Stream.listen](stream/listen) to get the actual data.

``` {.language-dart data-language="dart"}
Stream<List<int>> stream = File('quotes.txt').openRead();
stream.transform(utf8.decoder).forEach(print);
```

This stream emits a sequence of lists of bytes. The program must then
handle those lists of bytes in some way. Here, the code uses a UTF-8
decoder (provided in the `dart:convert` library) to convert the sequence
of bytes into a sequence of Dart strings.

Another common use of streams is for user-generated events in a web app:
The following code listens for mouse clicks on a button.

``` {.language-dart data-language="dart"}
querySelector('#myButton')!.onClick.forEach((_) => print('Click.'));
```

Other resources
---------------

-   The [dart:async section of the library
    tour](https://dart.dev/guides/libraries/library-tour#dartasync---asynchronous-programming):
    A brief overview of asynchronous programming.

-   [Use Future-Based APIs](https://dart.dev/codelabs/async-await): A
    closer look at Futures and how to use them to write asynchronous
    Dart code.

-   [Futures and Error
    Handling](https://dart.dev/guides/libraries/futures-error-handling):
    Everything you wanted to know about handling errors and exceptions
    when working with Futures (but were afraid to ask).

-   [The Event Loop and Dart](https://dart.dev/articles/event-loop/):
    Learn how Dart handles the event queue and microtask queue, so you
    can write better asynchronous code with fewer surprises.

-   [test package: Asynchronous Tests](https://pub.dev/packages/test):
    How to test asynchronous code.

Classes
-------

[Completer](completer-class)\<T\>
:   A way to produce Future objects and to complete them later with a
    value or error.

[DeferredLibrary](deferredlibrary-class){.deprecated}
:   Indicates that loading of [libraryName](deferredlibrary/libraryname)
    is deferred.

[EventSink](eventsink-class)\<T\>
:   A [Sink](../dart-core/sink-class) that supports adding errors.

[Future](future-class)\<T\>
:   The result of an asynchronous computation.

[FutureOr](futureor-class)\<T\>
:   A type representing values that are either `Future<T>` or `T`.

[MultiStreamController](multistreamcontroller-class)\<T\>
:   An enhanced stream controller provided by
    [Stream.multi](stream/stream.multi).

[Stream](stream-class)\<T\>
:   A source of asynchronous data events.

[StreamConsumer](streamconsumer-class)\<S\>
:   Abstract interface for a \"sink\" accepting multiple entire streams.

[StreamController](streamcontroller-class)\<T\>
:   A controller with the stream it controls.

[StreamIterator](streamiterator-class)\<T\>
:   An [Iterator](../dart-core/iterator-class)-like interface for the
    values of a [Stream](stream-class).

[StreamSink](streamsink-class)\<S\>
:   A object that accepts stream events both synchronously and
    asynchronously.

[StreamSubscription](streamsubscription-class)\<T\>
:   A subscription on events from a [Stream](stream-class).

[StreamTransformer](streamtransformer-class)\<S, T\>
:   Transforms a Stream.

[StreamTransformerBase](streamtransformerbase-class)\<S, T\>
:   Base class for implementing
    [StreamTransformer](streamtransformer-class).

[StreamView](streamview-class)\<T\>
:   [Stream](stream-class) wrapper that only exposes the
    [Stream](stream-class) interface.

[SynchronousStreamController](synchronousstreamcontroller-class)\<T\>
:   A stream controller that delivers its events synchronously.

[Timer](timer-class)
:   A countdown timer that can be configured to fire once or repeatedly.

[Zone](zone-class)
:   A zone represents an environment that remains stable across
    asynchronous calls.

[ZoneDelegate](zonedelegate-class)
:   An adapted view of the parent zone.

[ZoneSpecification](zonespecification-class)
:   A parameter object with custom zone function handlers for
    [Zone.fork](zone/fork).

Extensions
----------

[FutureExtensions](futureextensions)
:   Convenience methods on futures.

Functions
---------

[runZoned](runzoned)\<R\>(R body(),
{[Map](../dart-core/map-class)\<[Object](../dart-core/object-class)?,
[Object](../dart-core/object-class)?\>? zoneValues,
[ZoneSpecification](zonespecification-class)? zoneSpecification,
[Function](../dart-core/function-class)? onError}) → R

Runs `body` in its own zone.

[runZonedGuarded](runzonedguarded)\<R\>(R body(), void
onError([Object](../dart-core/object-class) error,
[StackTrace](../dart-core/stacktrace-class) stack),
{[Map](../dart-core/map-class)\<[Object](../dart-core/object-class)?,
[Object](../dart-core/object-class)?\>? zoneValues,
[ZoneSpecification](zonespecification-class)? zoneSpecification}) → R?

::: {.features}
\@Since(\"2.8\")
:::

Runs `body` in its own error zone.

[scheduleMicrotask](schedulemicrotask)(void callback()) → void

Runs a function asynchronously.

[unawaited](unawaited)([Future](future-class)\<void\>? future) → void

::: {.features}
\@Since(\"2.15\")
:::

Explicitly ignores a future.

Typedefs
--------

[ControllerCallback](controllercallback) = void Function()

Type of a stream controller\'s `onListen`, `onPause` and `onResume`
callbacks.

[ControllerCancelCallback](controllercancelcallback) =
[FutureOr](futureor-class)\<void\> Function()

Type of stream controller `onCancel` callbacks.

[CreatePeriodicTimerHandler](createperiodictimerhandler) =
[Timer](timer-class) Function([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone,
[Duration](../dart-core/duration-class) period, void
f([Timer](timer-class) timer))

The type of a custom
[Zone.createPeriodicTimer](zone/createperiodictimer) implementation
function.

[CreateTimerHandler](createtimerhandler) = [Timer](timer-class)
Function([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class)
parent, [Zone](zone-class) zone, [Duration](../dart-core/duration-class)
duration, void f())

The type of a custom [Zone.createTimer](zone/createtimer) implementation
function.

[ErrorCallbackHandler](errorcallbackhandler) =
[AsyncError](asyncerror-class)? Function([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone,
[Object](../dart-core/object-class) error,
[StackTrace](../dart-core/stacktrace-class)? stackTrace)

The type of a custom [Zone.errorCallback](zone/errorcallback)
implementation function.

[ForkHandler](forkhandler) = [Zone](zone-class)
Function([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class)
parent, [Zone](zone-class) zone,
[ZoneSpecification](zonespecification-class)? specification,
[Map](../dart-core/map-class)\<[Object](../dart-core/object-class)?,
[Object](../dart-core/object-class)?\>? zoneValues)

The type of a custom [Zone.fork](zone/fork) implementation function.

[HandleUncaughtErrorHandler](handleuncaughterrorhandler) = void
Function([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class)
parent, [Zone](zone-class) zone, [Object](../dart-core/object-class)
error, [StackTrace](../dart-core/stacktrace-class) stackTrace)

The type of a custom
[Zone.handleUncaughtError](zone/handleuncaughterror) implementation
function.

[PrintHandler](printhandler) = void Function([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone,
[String](../dart-core/string-class) line)

The type of a custom [Zone.print](zone/print) implementation function.

[RegisterBinaryCallbackHandler](registerbinarycallbackhandler) =
[ZoneBinaryCallback](zonebinarycallback)\<R, T1, T2\> Function\<R, T1,
T2\>([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class) parent,
[Zone](zone-class) zone, R f(T1 arg1, T2 arg2))

The type of a custom
[Zone.registerBinaryCallback](zone/registerbinarycallback)
implementation function.

[RegisterCallbackHandler](registercallbackhandler) =
[ZoneCallback](zonecallback)\<R\> Function\<R\>([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone, R
f())

The type of a custom [Zone.registerCallback](zone/registercallback)
implementation function.

[RegisterUnaryCallbackHandler](registerunarycallbackhandler) =
[ZoneUnaryCallback](zoneunarycallback)\<R, T\> Function\<R,
T\>([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class) parent,
[Zone](zone-class) zone, R f(T arg))

The type of a custom
[Zone.registerUnaryCallback](zone/registerunarycallback) implementation
function.

[RunBinaryHandler](runbinaryhandler) = R Function\<R, T1,
T2\>([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class) parent,
[Zone](zone-class) zone, R f(T1 arg1, T2 arg2), T1 arg1, T2 arg2)

The type of a custom [Zone.runBinary](zone/runbinary) implementation
function.

[RunHandler](runhandler) = R Function\<R\>([Zone](zone-class) self,
[ZoneDelegate](zonedelegate-class) parent, [Zone](zone-class) zone, R
f())

The type of a custom [Zone.run](zone/run) implementation function.

[RunUnaryHandler](rununaryhandler) = R Function\<R,
T\>([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class) parent,
[Zone](zone-class) zone, R f(T arg), T arg)

The type of a custom [Zone.runUnary](zone/rununary) implementation
function.

[ScheduleMicrotaskHandler](schedulemicrotaskhandler) = void
Function([Zone](zone-class) self, [ZoneDelegate](zonedelegate-class)
parent, [Zone](zone-class) zone, void f())

The type of a custom [Zone.scheduleMicrotask](zone/schedulemicrotask)
implementation function.

[ZoneBinaryCallback](zonebinarycallback)\<R, T1, T2\> = R Function(T1
arg1, T2 arg2)

[ZoneCallback](zonecallback)\<R\> = R Function()

[ZoneUnaryCallback](zoneunarycallback)\<R, T\> = R Function(T arg)

Exceptions / Errors {#exceptions}
-------------------

[AsyncError](asyncerror-class)
:   An error and a stack trace.

[DeferredLoadException](deferredloadexception-class)
:   Thrown when a deferred library fails to load.

[TimeoutException](timeoutexception-class)
:   Thrown when a scheduled timeout happens while waiting for an async
    result.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/dart-async-library.html>
:::
