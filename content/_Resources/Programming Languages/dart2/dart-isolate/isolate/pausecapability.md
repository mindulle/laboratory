[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

pauseCapability property
========================

::: {.section .multi-line-signature}
[Capability](../capability-class)? pauseCapability

::: {.features}
final
:::
:::

Capability granting the ability to pause the isolate.

This capability is required by [pause](pause). If the capability is
`null`, or if it is not the correct pause capability of the isolate
identified by [controlPort](controlport), then calls to [pause](pause)
will have no effect.

If the isolate is spawned in a paused state, use this capability as
argument to the [resume](resume) method in order to resume the paused
isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final Capability? pauseCapability;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/pauseCapability.html>
:::
