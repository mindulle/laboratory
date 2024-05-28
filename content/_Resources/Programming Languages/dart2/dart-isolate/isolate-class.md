[dart:isolate](../dart-isolate/dart-isolate-library){._links-link}

Isolate class
=============

An isolated Dart execution context.

All Dart code runs in an isolate, and code can access classes and values
only from the same isolate. Different isolates can communicate by
sending values through ports (see [ReceivePort](receiveport-class),
[SendPort](sendport-class)).

An `Isolate` object is a reference to an isolate, usually different from
the current isolate. It represents, and can be used to control, the
other isolate.

When spawning a new isolate, the spawning isolate receives an `Isolate`
object representing the new isolate when the spawn operation succeeds.

Isolates run code in its own event loop, and each event may run smaller
tasks in a nested microtask queue.

An `Isolate` object allows other isolates to control the event loop of
the isolate that it represents, and to inspect the isolate, for example
by pausing the isolate or by getting events when the isolate has an
uncaught error.

The [controlPort](isolate/controlport) identifies and gives access to
controlling the isolate, and the
[pauseCapability](isolate/pausecapability) and
[terminateCapability](isolate/terminatecapability) guard access to some
control operations. For example, calling [pause](isolate/pause) on an
`Isolate` object created without a
[pauseCapability](isolate/pausecapability), has no effect.

The `Isolate` object provided by a spawn operation will have the control
port and capabilities needed to control the isolate. New isolate objects
can be created without some of these capabilities if necessary, using
the [Isolate.Isolate](isolate/isolate) constructor.

An `Isolate` object cannot be sent over a `SendPort`, but the control
port and capabilities can be sent, and can be used to create a new
functioning `Isolate` object in the receiving port\'s isolate.

Constructors
------------

[Isolate](isolate/isolate)([SendPort](sendport-class) controlPort, {[Capability](capability-class)? pauseCapability, [Capability](capability-class)? terminateCapability})
:   Creates a new [Isolate](isolate-class) object with a restricted set
    of capabilities.

Properties {#instance-properties}
----------

[controlPort](isolate/controlport) → [SendPort](sendport-class)

::: {.features}
final
:::

Control port used to send control messages to the isolate.

[debugName](isolate/debugname) → [String](../dart-core/string-class)?

::: {.features}
\@Since(\"2.3\"), read-only
:::

The name of the [Isolate](isolate-class) displayed for debug purposes.

[errors](isolate/errors) → [Stream](../dart-async/stream-class)

::: {.features}
read-only
:::

Returns a broadcast stream of uncaught errors from the isolate.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[pauseCapability](isolate/pausecapability) →
[Capability](capability-class)?

::: {.features}
final
:::

Capability granting the ability to pause the isolate.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[terminateCapability](isolate/terminatecapability) →
[Capability](capability-class)?

::: {.features}
final
:::

Capability granting the ability to terminate the isolate.

Methods {#instance-methods}
-------

[addErrorListener](isolate/adderrorlistener)([SendPort](sendport-class)
port) → void

Requests that uncaught errors of the isolate are sent back to `port`.

[addOnExitListener](isolate/addonexitlistener)([SendPort](sendport-class)
responsePort, {[Object](../dart-core/object-class)? response}) → void

Requests an exit message on `responsePort` when the isolate terminates.

[kill](isolate/kill)({[int](../dart-core/int-class) priority =
beforeNextEvent}) → void

Requests the isolate to shut down.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pause](isolate/pause)(\[[Capability](capability-class)?
resumeCapability\]) → [Capability](capability-class)

Requests the isolate to pause.

[ping](isolate/ping)([SendPort](sendport-class) responsePort,
{[Object](../dart-core/object-class)? response,
[int](../dart-core/int-class) priority = immediate}) → void

Requests that the isolate send `response` on the `responsePort`.

[removeErrorListener](isolate/removeerrorlistener)([SendPort](sendport-class)
port) → void

Stops listening for uncaught errors from the isolate.

[removeOnExitListener](isolate/removeonexitlistener)([SendPort](sendport-class)
responsePort) → void

Stops listening for exit messages from the isolate.

[resume](isolate/resume)([Capability](capability-class)
resumeCapability) → void

Resumes a paused isolate.

[setErrorsFatal](isolate/seterrorsfatal)([bool](../dart-core/bool-class)
errorsAreFatal) → void

Sets whether uncaught errors will terminate the isolate.

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

[current](isolate/current) → [Isolate](isolate-class)

::: {.features}
read-only
:::

An [Isolate](isolate-class) object representing the current isolate.

[packageConfig](isolate/packageconfig) →
[Future](../dart-async/future-class)\<[Uri](../dart-core/uri-class)?\>

::: {.features}
read-only
:::

The location of the package configuration of the current isolate, if
any.

Static Methods
--------------

[exit](isolate/exit)(\[[SendPort](sendport-class)? finalMessagePort, [Object](../dart-core/object-class)? message\]) → Never
:   Terminates the current isolate synchronously.

[resolvePackageUri](isolate/resolvepackageuri)([Uri](../dart-core/uri-class) packageUri) → [Future](../dart-async/future-class)\<[Uri](../dart-core/uri-class)?\>
:   Maps a `package:` URI to a non-package Uri.

[spawn](isolate/spawn)\<T\>(void entryPoint(T message), T message, {[bool](../dart-core/bool-class) paused = false, [bool](../dart-core/bool-class) errorsAreFatal = true, [SendPort](sendport-class)? onExit, [SendPort](sendport-class)? onError, [String](../dart-core/string-class)? debugName}) → [Future](../dart-async/future-class)\<[Isolate](isolate-class)\>
:   Creates and spawns an isolate that shares the same code as the
    current isolate.

[spawnUri](isolate/spawnuri)([Uri](../dart-core/uri-class) uri, [List](../dart-core/list-class)\<[String](../dart-core/string-class)\> args, dynamic message, {[bool](../dart-core/bool-class) paused = false, [SendPort](sendport-class)? onExit, [SendPort](sendport-class)? onError, [bool](../dart-core/bool-class) errorsAreFatal = true, [bool](../dart-core/bool-class)? checked, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? environment, [Uri](../dart-core/uri-class)? packageRoot, [Uri](../dart-core/uri-class)? packageConfig, [bool](../dart-core/bool-class) automaticPackageResolution = false, [String](../dart-core/string-class)? debugName}) → [Future](../dart-async/future-class)\<[Isolate](isolate-class)\>
:   Creates and spawns an isolate that runs the code from the library
    with the specified URI.

Constants
---------

[beforeNextEvent](isolate/beforenextevent-constant) → const [int](../dart-core/int-class)
:   Argument to `ping` and `kill`: Ask for action before the next event.
    <div>

    `1`

    </div>

[immediate](isolate/immediate-constant) → const [int](../dart-core/int-class)
:   Argument to `ping` and `kill`: Ask for immediate action.
    <div>

    `0`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate-class.html>
:::
