[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

terminateCapability property
============================

::: {.section .multi-line-signature}
[Capability](../capability-class)? terminateCapability

::: {.features}
final
:::
:::

Capability granting the ability to terminate the isolate.

This capability is required by [kill](kill) and
[setErrorsFatal](seterrorsfatal). If the capability is `null`, or if it
is not the correct termination capability of the isolate identified by
[controlPort](controlport), then calls to those methods will have no
effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final Capability? terminateCapability;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/terminateCapability.html>
:::
