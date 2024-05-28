[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

setErrorsFatal method
=====================

::: {.section .multi-line-signature}
void setErrorsFatal(

1.  [bool](../../dart-core/bool-class) errorsAreFatal

)
:::

Sets whether uncaught errors will terminate the isolate.

If errors are fatal, any uncaught error will terminate the isolate event
loop and shut down the isolate.

This call requires the [terminateCapability](terminatecapability) for
the isolate. If the capability is absent or incorrect, no change is
made.

Since isolates run concurrently, it\'s possible for the receiving
isolate to exit due to an error, before a request, using this method,
has been received and processed. To avoid this, either use the
corresponding parameter to the spawn function, or start the isolate
paused, set errors non-fatal and then resume the isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void setErrorsFatal(bool errorsAreFatal);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/setErrorsFatal.html>
:::
