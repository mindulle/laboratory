[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Finalizable class
=================

Marker interface for objects which should not be finalized too soon.

Any local variable with a static type that *includes `Finalizable`* is
guaranteed to be alive until execution exits the code block where the
variable is in scope.

A type *includes `Finalizable`* if either

-   the type is a non-`Never` subtype of `Finalizable`, or
-   the type is `T?` or `FutureOr<T>` where `T` includes `Finalizable`.

In other words, while an object is referenced by such a variable, it is
guaranteed to *not* be considered unreachable, and the variable itself
is considered alive for the entire duration of its scope, even after it
is last referenced.

*Without this marker interface on the variable\'s type, a variable\'s
value might be garbage collected before the surrounding scope has been
completely executed, as long as the variable is definitely not
referenced again. That can, in turn, trigger a `NativeFinalizer` to
perform a callback. When the variable\'s type includes
[Finalizable](finalizable-class), The `NativeFinalizer` callback is
prevented from running until the current code using that variable is
complete.*

For example, `finalizable` is kept alive during the execution of
`someNativeCall`:

``` {.language-dart data-language="dart"}
void myFunction() {
  final finalizable = MyFinalizable(Pointer.fromAddress(0));
  someNativeCall(finalizable.nativeResource);
}

void someNativeCall(Pointer nativeResource) {
  // ..
}

class MyFinalizable implements Finalizable {
  final Pointer nativeResource;

  MyFinalizable(this.nativeResource);
}
```

Methods on a class implementing `Finalizable` keep the `this` object
alive for the duration of the method execution. *The `this` value is
treated like a local variable.*

For example, `this` is kept alive during the execution of
`someNativeCall` in `myFunction`:

``` {.language-dart data-language="dart"}
class MyFinalizable implements Finalizable {
  final Pointer nativeResource;

  MyFinalizable(this.nativeResource);

  void myFunction() {
    someNativeCall(nativeResource);
  }
}

void someNativeCall(Pointer nativeResource) {
  // ..
}
```

It is good practise to implement logic involving finalizables as methods
on the class that implements [Finalizable](finalizable-class).

If a closure is created inside the block scope declaring the variable,
and that closure contains any reference to the variable, the variable
stays alive as long as the closure object does, or as long as the body
of such a closure is executing.

For example, `finalizable` is kept alive by the closure object and until
the end of the closure body:

``` {.language-dart data-language="dart"}
void doSomething() {
  final resourceAction = myFunction();
  resourceAction(); // `finalizable` is alive until this call returns.
}

void Function() myFunction() {
  final finalizable = MyFinalizable(Pointer.fromAddress(0));
  return () {
    someNativeCall(finalizable.nativeResource);
  };
}

void someNativeCall(Pointer nativeResource) {
  // ..
}

class MyFinalizable implements Finalizable {
  final Pointer nativeResource;

  MyFinalizable(this.nativeResource);
}
```

Only captured variables are kept alive by closures, not all variables.

For example, `finalizable` is not kept alive by the returned closure
object:

``` {.language-dart data-language="dart"}
void Function() myFunction() {
  final finalizable = MyFinalizable(Pointer.fromAddress(0));
  final nativeResource = finalizable.nativeResource;
  return () {
    someNativeCall(nativeResource);
  };
}

void someNativeCall(Pointer nativeResource) {
  // ..
}

class MyFinalizable implements Finalizable {
  final Pointer nativeResource;

  MyFinalizable(this.nativeResource);
}
```

It\'s likely an error if a resource extracted from a finalizable object
escapes the scope of the finalizable variable it\'s taken from.

The behavior of `Finalizable` variables applies to asynchronous
functions too. Such variables are kept alive as long as any code may
still execute inside the scope that declared the variable, or in a
closure capturing the variable, even if there are asynchronous delays
during that execution.

For example, `finalizable` is kept alive during the
`await someAsyncCall()`:

``` {.language-dart data-language="dart"}
Future<void> myFunction() async {
  final finalizable = MyFinalizable();
  await someAsyncCall();
}

Future<void> someAsyncCall() async {
  // ..
}

class MyFinalizable implements Finalizable {
  // ..
}
```

Also in asynchronous code it\'s likely an error if a resource extracted
from a finalizable object escapes the scope of the finalizable variable
it\'s taken from. If you have to extract a resource from a
`Finalizable`, you should ensure the scope in which Finalizable is
defined outlives the resource by `await`ing any asynchronous code that
uses the resource.

For example, `this` is kept alive until `resource` is not used anymore
in `useAsync1`, but not in `useAsync2` and `useAsync3`:

``` {.language-dart data-language="dart"}
class MyFinalizable {
  final Pointer<Int8> resource;

  MyFinalizable(this.resource);

  Future<int> useAsync1() async {
    return await useResource(resource);
  }

  Future<int> useAsync2() async {
    return useResource(resource);
  }

  Future<int> useAsync3() {
    return useResource(resource);
  }
}

/// Does not use [resource] after the returned future completes.
Future<int> useResource(Pointer<Int8> resource) async {
  return resource.value;
}
```

*It is possible for an asynchronous function to *stall* at an `await`,
such that the runtime system can see that there is no possible way for
that `await` to complete. In that case, no code after the `await` will
ever execute, including `finally` blocks, and the variable may be
considered dead along with everything else.*

If you\'re not going to keep a variable alive yourself, make sure to
pass the finalizable object to other functions instead of just its
resource.

For example, `finalizable` is not kept alive by `myFunction` after it
has run to the end of its scope, while `someAsyncCall` could still
continue execution. However, `finalizable` is kept alive by
`someAsyncCall` itself:

``` {.language-dart data-language="dart"}
void myFunction() {
  final finalizable = MyFinalizable();
  someAsyncCall(finalizable);
}

Future<void> someAsyncCall(MyFinalizable finalizable) async {
  // ..
}

class MyFinalizable implements Finalizable {
  // ..
}
```

Annotations

:   -   \@Since(\'2.17\')

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Finalizable-class.html>
:::
