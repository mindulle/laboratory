[dart:async](../dart-async/dart-async-library){._links-link}

Future\<T\> class
=================

The result of an asynchronous computation.

An *asynchronous computation* cannot provide a result immediately when
it is started, unlike a synchronous computation which does compute a
result immediately by either returning a value or by throwing. An
asynchronous computation may need to wait for something external to the
program (reading a file, querying a database, fetching a web page) which
takes time. Instead of blocking all computation until the result is
available, the asynchronous computation immediately returns a `Future`
which will *eventually* \"complete\" with the result.

### Asynchronous programming

To perform an asynchronous computation, you use an `async` function
which always produces a future. Inside such an asynchronous function,
you can use the `await` operation to delay execution until another
asynchronous computation has a result. While execution of the awaiting
function is delayed, the program is not blocked, and can continue doing
other things.

Example:

``` {.language-dart data-language="dart"}
import "dart:io";
Future<bool> fileContains(String path, String needle) async {
   var haystack = await File(path).readAsString();
   return haystack.contains(needle);
}
```

Here the `File.readAsString` method from `dart:io` is an asychronous
function returning a `Future<String>`. The `fileContains` function is
marked with `async` right before its body, which means that you can use
`await` inside it, and that it must return a future. The call to
`File(path).readAsString()` initiates reading the file into a string and
produces a `Future<String>` which will eventually contain the result.
The `await` then waits for that future to complete with a string (or an
error, if reading the file fails). While waiting, the program can do
other things. When the future completes with a string, the
`fileContains` function computes a boolean and returns it, which then
completes the original future that it returned when first called.

If a future completes with an *error*, awaiting that future will
(re-)throw that error. In the example here, we can add error checking:

``` {.language-dart data-language="dart"}
import "dart:io";
Future<bool> fileContains(String path, String needle) async {
  try {
    var haystack = await File(path).readAsString();
    return haystack.contains(needle);
  } on FileSystemException catch (exception, stack) {
    _myLog.logError(exception, stack);
    return false;
  }
}
```

You use a normal `try`/`catch` to catch the failures of awaited
asynchronous computations.

In general, when writing asynchronous code, you should always await a
future when it is produced, and not wait until after another
asynchronous delay. That ensures that you are ready to receive any error
that the future might produce, which is important because an
asynchronous error that no-one is awaiting is an *uncaught* error and
may terminate the running program.

### Programming with the `Future` API. {#programming-with-the-future-api}

The `Future` class also provides a more direct, low-level functionality
for accessing the result that it completes with. The `async` and `await`
language features are built on top of this functionality, and it
sometimes makes sense to use it directly. There are things that you
cannot do by just `await`ing one future at a time.

With a [Future](future-class), you can manually register callbacks that
handle the value, or error, once it is available. For example:

``` {.language-dart data-language="dart"}
Future<int> future = getFuture();
future.then((value) => handleValue(value))
      .catchError((error) => handleError(error));
```

Since a [Future](future-class) can be completed in two ways, either with
a value (if the asynchronous computation succeeded) or with an error (if
the computation failed), you can install callbacks for either or both
cases.

In some cases we say that a future is completed *with another future*.
This is a short way of stating that the future is completed in the same
way, with the same value or error, as the other future once that other
future itself completes. Most functions in the platform libraries that
complete a future (for example [Completer.complete](completer/complete)
or [Future.value](future/future.value)), also accepts another future,
and automatically handles forwarding the result to the future being
completed.

The result of registering callbacks is itself a `Future`, which in turn
is completed with the result of invoking the corresponding callback with
the original future\'s result. The new future is completed with an error
if the invoked callback throws. For example:

``` {.language-dart data-language="dart"}
Future<int> successor = future.then((int value) {
    // Invoked when the future is completed with a value.
    return 42;  // The successor is completed with the value 42.
  },
  onError: (e) {
    // Invoked when the future is completed with an error.
    if (canHandle(e)) {
      return 499;  // The successor is completed with the value 499.
    } else {
      throw e;  // The successor is completed with the error e.
    }
  });
```

If a future does not have any registered handler when it completes with
an error, it forwards the error to an \"uncaught-error handler\". This
behavior ensures that no error is silently dropped. However, it also
means that error handlers should be installed early, so that they are
present as soon as a future is completed with an error. The following
example demonstrates this potential bug:

``` {.language-dart data-language="dart"}
var future = getFuture();
Timer(const Duration(milliseconds: 5), () {
  // The error-handler is not attached until 5 ms after the future has
  // been received. If the future fails before that, the error is
  // forwarded to the global error-handler, even though there is code
  // (just below) to eventually handle the error.
  future.then((value) { useValue(value); },
              onError: (e) { handleError(e); });
});
```

When registering callbacks, it\'s often more readable to register the
two callbacks separately, by first using [then](future/then) with one
argument (the value handler) and using a second
[catchError](future/catcherror) for handling errors. Each of these will
forward the result that they don\'t handle to their successors, and
together they handle both value and error result. It has the additional
benefit of the [catchError](future/catcherror) handling errors in the
[then](future/then) value callback too. Using sequential handlers
instead of parallel ones often leads to code that is easier to reason
about. It also makes asynchronous code very similar to synchronous code:

``` {.language-dart data-language="dart"}
// Synchronous code.
try {
  int value = foo();
  return bar(value);
} catch (e) {
  return 499;
}
```

Equivalent asynchronous code, based on futures:

``` {.language-dart data-language="dart"}
Future<int> asyncValue = Future(foo);  // Result of foo() as a future.
asyncValue.then((int value) {
  return bar(value);
}).catchError((e) {
  return 499;
});
```

Similar to the synchronous code, the error handler (registered with
[catchError](future/catcherror)) is handling any errors thrown by either
`foo` or `bar`. If the error-handler had been registered as the
`onError` parameter of the `then` call, it would not catch errors from
the `bar` call.

Futures can have more than one callback-pair registered. Each successor
is treated independently and is handled as if it was the only successor.

A future may also fail to ever complete. In that case, no callbacks are
called. That situation should generally be avoided if possible, unless
it\'s very clearly documented.

Available Extensions

:   -   [FutureExtensions](futureextensions)

Constructors
------------

[Future](future/future)([FutureOr](futureor-class)\<T\> computation())

::: {.constructor-modifier .features}
factory
:::

Creates a future containing the result of calling `computation`
asynchronously with [Timer.run](timer/run).

[Future.delayed](future/future.delayed)([Duration](../dart-core/duration-class)
duration, \[[FutureOr](futureor-class)\<T\> computation()?\])

::: {.constructor-modifier .features}
factory
:::

Creates a future that runs its computation after a delay.

[Future.error](future/future.error)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\])

::: {.constructor-modifier .features}
factory
:::

Creates a future that completes with an error.

[Future.microtask](future/future.microtask)([FutureOr](futureor-class)\<T\>
computation())

::: {.constructor-modifier .features}
factory
:::

Creates a future containing the result of calling `computation`
asynchronously with [scheduleMicrotask](schedulemicrotask).

[Future.sync](future/future.sync)([FutureOr](futureor-class)\<T\>
computation())

::: {.constructor-modifier .features}
factory
:::

Returns a future containing the result of immediately calling
`computation`.

[Future.value](future/future.value)(\[[FutureOr](futureor-class)\<T\>?
value\])

::: {.constructor-modifier .features}
factory
:::

Creates a future completed with `value`.

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

[asStream](future/asstream)() → [Stream](stream-class)\<T\>

Creates a [Stream](stream-class) containing the result of this future.

[catchError](future/catcherror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class)
test([Object](../dart-core/object-class) error)?}) →
[Future](future-class)\<T\>

Handles errors emitted by this [Future](future-class).

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[then](future/then)\<R\>([FutureOr](futureor-class)\<R\> onValue(T
value), {[Function](../dart-core/function-class)? onError}) →
[Future](future-class)\<R\>

Register callbacks to be called when this future completes.

[timeout](future/timeout)([Duration](../dart-core/duration-class)
timeLimit, {[FutureOr](futureor-class)\<T\> onTimeout()?}) →
[Future](future-class)\<T\>

Time-out the future computation after `timeLimit` has passed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[whenComplete](future/whencomplete)([FutureOr](futureor-class)\<void\>
action()) → [Future](future-class)\<T\>

Registers a function to be called when this future completes.

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

[any](future/any)\<T\>([Iterable](../dart-core/iterable-class)\<[Future](future-class)\<T\>\> futures) → [Future](future-class)\<T\>
:   Returns the result of the first future in `futures` to complete.

[doWhile](future/dowhile)([FutureOr](futureor-class)\<[bool](../dart-core/bool-class)\> action()) → [Future](future-class)
:   Performs an operation repeatedly until it returns `false`.

[forEach](future/foreach)\<T\>([Iterable](../dart-core/iterable-class)\<T\> elements, [FutureOr](futureor-class) action(T element)) → [Future](future-class)
:   Performs an action for each element of the iterable, in turn.

[wait](future/wait)\<T\>([Iterable](../dart-core/iterable-class)\<[Future](future-class)\<T\>\> futures, {[bool](../dart-core/bool-class) eagerError = false, void cleanUp(T successValue)?}) → [Future](future-class)\<[List](../dart-core/list-class)\<T\>\>
:   Waits for multiple futures to complete and collects their results.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future-class.html>
:::
