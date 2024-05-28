[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

resume method
=============

::: {.section .multi-line-signature}
void resume(

1.  [Capability](../capability-class) resumeCapability

)
:::

Resumes a paused isolate.

Sends a message to an isolate requesting that it ends a pause that was
previously requested.

When all active pause requests have been cancelled, the isolate will
continue processing events and handling normal messages.

If the `resumeCapability` is not one that has previously been used to
pause the isolate, or it has already been used to resume from that
pause, the resume call has no effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void resume(Capability resumeCapability);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/resume.html>
:::
