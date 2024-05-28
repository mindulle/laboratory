[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

spawnUri method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Isolate](../isolate-class)\>
spawnUri(

1.  [Uri](../../dart-core/uri-class) uri,
2.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    args,
3.  dynamic message,
4.  {[bool](../../dart-core/bool-class) paused = false,
5.  [SendPort](../sendport-class)? onExit,
6.  [SendPort](../sendport-class)? onError,
7.  [bool](../../dart-core/bool-class) errorsAreFatal = true,
8.  [bool](../../dart-core/bool-class)? checked,
9.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\>? environment,
10. @[Deprecated](../../dart-core/deprecated-class)(\'The packages/ dir
    is not supported in Dart 2\') [Uri](../../dart-core/uri-class)?
    packageRoot,
11. [Uri](../../dart-core/uri-class)? packageConfig,
12. [bool](../../dart-core/bool-class) automaticPackageResolution =
    false,
13. \@Since(\"2.3\") [String](../../dart-core/string-class)? debugName}

)
:::

Creates and spawns an isolate that runs the code from the library with
the specified URI.

The isolate starts executing the top-level `main` function of the
library with the given URI.

The target `main` must be callable with zero, one or two arguments.
Examples:

-   `main()`
-   `main(args)`
-   `main(args, message)`

When present, the parameter `args` is set to the provided `args` list.
When present, the parameter `message` is set to the initial `message`.

If the `paused` parameter is set to `true`, the isolate will start up in
a paused state, as if by an initial call of
`isolate.pause(isolate.pauseCapability)`. To resume the isolate, call
`isolate.resume(isolate.pauseCapability)`.

If the `errorsAreFatal`, `onExit` and/or `onError` parameters are
provided, the isolate will act as if, respectively,
[setErrorsFatal](seterrorsfatal), [addOnExitListener](addonexitlistener)
and [addErrorListener](adderrorlistener) were called with the
corresponding parameter and was processed before the isolate starts
running.

You can also call the [setErrorsFatal](seterrorsfatal),
[addOnExitListener](addonexitlistener) and
[addErrorListener](adderrorlistener) methods on the returned isolate,
but unless the isolate was started as `paused`, it may already have
terminated before those methods can complete.

If the `checked` parameter is set to `true` or `false`, the new isolate
will run code in checked mode (enabling asserts and type checks),
respectively in production mode (disabling asserts and type checks), if
possible. If the parameter is omitted, the new isolate will inherit the
value from the current isolate.

In Dart2 strong mode, the `checked` parameter only controls asserts, but
not type checks.

It may not always be possible to honor the `checked` parameter. If the
isolate code was pre-compiled, it may not be possible to change the
checked mode setting dynamically. In that case, the `checked` parameter
is ignored.

WARNING: The `checked` parameter is not implemented on all platforms
yet.

If the `packageConfig` parameter is provided, then it is used to find
the location of a package resolution configuration file for the spawned
isolate.

If the `automaticPackageResolution` parameter is provided, then the
location of the package sources in the spawned isolate is automatically
determined.

The `environment` is a mapping from strings to strings which the spawned
isolate uses when looking up
[String.fromEnvironment](../../dart-core/string/string.fromenvironment)
values. The system may add its own entries to environment as well. If
`environment` is omitted, the spawned isolate has the same environment
declarations as the spawning isolate.

WARNING: The `environment` parameter is not implemented on all platforms
yet.

If `debugName` is provided, the spawned `Isolate` will be identifiable
by this name in debuggers and logging.

Returns a future that will complete with an `Isolate` instance if the
spawning succeeded. It will complete with an error otherwise.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<Isolate> spawnUri(
    Uri uri,
    List<String> args,
    var message,
    {bool paused = false,
    SendPort? onExit,
    SendPort? onError,
    bool errorsAreFatal = true,
    bool? checked,
    Map<String, String>? environment,
    @Deprecated('The packages/ dir is not supported in Dart 2')
        Uri? packageRoot,
    Uri? packageConfig,
    bool automaticPackageResolution = false,
    @Since("2.3")
        String? debugName});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/spawnUri.html>
:::
