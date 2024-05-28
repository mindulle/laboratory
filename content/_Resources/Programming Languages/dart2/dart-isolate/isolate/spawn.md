[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

spawn\<T\> method
=================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Isolate](../isolate-class)\>
spawn\<T\>(

1.  void entryPoint(
    1.  T message

    ),
2.  T message,
3.  {[bool](../../dart-core/bool-class) paused = false,
4.  [bool](../../dart-core/bool-class) errorsAreFatal = true,
5.  [SendPort](../sendport-class)? onExit,
6.  [SendPort](../sendport-class)? onError,
7.  \@Since(\"2.3\") [String](../../dart-core/string-class)? debugName}

)
:::

Creates and spawns an isolate that shares the same code as the current
isolate.

The argument `entryPoint` specifies the initial function to call in the
spawned isolate. The entry-point function is invoked in the new isolate
with `message` as the only argument.

The function must be a top-level function or a static method that can be
called with a single argument, that is, a compile-time constant function
value which accepts at least one positional parameter and has at most
one required positional parameter. The function may accept any number of
optional parameters, as long as it *can* be called with just a single
argument. The function must not be the value of a function expression or
an instance method tear-off.

Usually the initial `message` contains a [SendPort](../sendport-class)
so that the spawner and spawnee can communicate with each other.

If the `paused` parameter is set to `true`, the isolate will start up in
a paused state, just before calling the `entryPoint` function with the
`message`, as if by an initial call of
`isolate.pause(isolate.pauseCapability)`. To resume the isolate, call
`isolate.resume(isolate.pauseCapability)`.

If the `errorsAreFatal`, `onExit` and/or `onError` parameters are
provided, the isolate will act as if, respectively,
[setErrorsFatal](seterrorsfatal), [addOnExitListener](addonexitlistener)
and [addErrorListener](adderrorlistener) were called with the
corresponding parameter and was processed before the isolate starts
running.

If `debugName` is provided, the spawned `Isolate` will be identifiable
by this name in debuggers and logging.

If `errorsAreFatal` is omitted, the platform may choose a default
behavior or inherit the current isolate\'s behavior.

You can also call the [setErrorsFatal](seterrorsfatal),
[addOnExitListener](addonexitlistener) and
[addErrorListener](adderrorlistener) methods on the returned isolate,
but unless the isolate was started as `paused`, it may already have
terminated before those methods can complete.

Returns a future which will complete with an `Isolate` instance if the
spawning succeeded. It will complete with an error otherwise.

One can expect the base memory overhead of an isolate to be in the order
of 30 kb.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<Isolate> spawn<T>(
    void entryPoint(T message), T message,
    {bool paused = false,
    bool errorsAreFatal = true,
    SendPort? onExit,
    SendPort? onError,
    @Since("2.3") String? debugName});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/spawn.html>
:::
