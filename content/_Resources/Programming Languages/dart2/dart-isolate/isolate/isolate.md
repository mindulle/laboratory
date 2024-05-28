[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

Isolate constructor
===================

::: {.section .multi-line-signature}
Isolate(

1.  [SendPort](../sendport-class) controlPort,
2.  {[Capability](../capability-class)? pauseCapability,
3.  [Capability](../capability-class)? terminateCapability}

)
:::

Creates a new [Isolate](../isolate-class) object with a restricted set
of capabilities.

The port should be a control port for an isolate, as taken from another
`Isolate` object.

The capabilities should be the subset of the capabilities that are
available to the original isolate. Capabilities of an isolate are locked
to that isolate, and have no effect anywhere else, so the capabilities
should come from the same isolate as the control port.

Can also be used to create an [Isolate](../isolate-class) object from a
control port, and any available capabilities, that have been sent
through a [SendPort](../sendport-class).

Example:

``` {.language-dart data-language="dart"}
Isolate isolate = findSomeIsolate();
Isolate restrictedIsolate = Isolate(isolate.controlPort);
untrustedCode(restrictedIsolate);
```

This example creates a new `Isolate` object that cannot be used to pause
or terminate the isolate. All the untrusted code can do is to inspect
the isolate and see uncaught errors or when it terminates.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Isolate(this.controlPort, {this.pauseCapability, this.terminateCapability});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/Isolate.html>
:::
