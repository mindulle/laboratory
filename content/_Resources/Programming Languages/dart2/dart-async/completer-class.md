[dart:async](../dart-async/dart-async-library){._links-link}

Completer\<T\> class
====================

A way to produce Future objects and to complete them later with a value
or error.

Most of the time, the simplest way to create a future is to just use one
of the [Future](future-class) constructors to capture the result of a
single asynchronous computation:

``` {.language-dart data-language="dart"}
Future(() { doSomething(); return result; });
```

or, if the future represents the result of a sequence of asynchronous
computations, they can be chained using [Future.then](future/then) or
similar functions on [Future](future-class):

``` {.language-dart data-language="dart"}
Future doStuff(){
  return someAsyncOperation().then((result) {
    return someOtherAsyncOperation(result);
  });
}
```

If you do need to create a Future from scratch --- for example, when
you\'re converting a callback-based API into a Future-based one --- you
can use a Completer as follows:

``` {.language-dart data-language="dart"}
class AsyncOperation {
  final Completer _completer = new Completer();

  Future<T> doOperation() {
    _startOperation();
    return _completer.future; // Send future object back to client.
  }

  // Something calls this when the value is ready.
  void _finishOperation(T result) {
    _completer.complete(result);
  }

  // If something goes wrong, call this.
  void _errorHappened(error) {
    _completer.completeError(error);
  }
}
```

Constructors
------------

[Completer](completer/completer)()

::: {.constructor-modifier .features}
factory
:::

Creates a new completer.

[Completer.sync](completer/completer.sync)()

::: {.constructor-modifier .features}
factory
:::

Completes the future synchronously.

Properties {#instance-properties}
----------

[future](completer/future) → [Future](future-class)\<T\>

::: {.features}
read-only
:::

The future that is completed by this completer.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isCompleted](completer/iscompleted) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the [future](completer/future) has been completed.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[complete](completer/complete)(\[[FutureOr](futureor-class)\<T\>?
value\]) → void

Completes [future](completer/future) with the supplied values.

[completeError](completer/completeerror)([Object](../dart-core/object-class)
error, \[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

Complete [future](completer/future) with an error.

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
<https://api.dart.dev/stable/2.18.5/dart-async/Completer-class.html>
:::
