[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

pause method
============

::: {.section .multi-line-signature}
[Capability](../capability-class) pause(

1.  \[[Capability](../capability-class)? resumeCapability\]

)
:::

Requests the isolate to pause.

When the isolate receives the pause command, it stops processing events
from the event loop queue. It may still add new events to the queue in
response to, e.g., timers or receive-port messages. When the isolate is
resumed, it starts handling the already enqueued events.

The pause request is sent through the isolate\'s command port, which
bypasses the receiving isolate\'s event loop. The pause takes effect
when it is received, pausing the event loop as it is at that time.

The `resumeCapability` is used to identity the pause, and must be used
again to end the pause using [resume](resume). If `resumeCapability` is
omitted, a new capability object is created and used instead.

If an isolate is paused more than once using the same capability, only
one resume with that capability is needed to end the pause.

If an isolate is paused using more than one capability, each pause must
be individually ended before the isolate resumes.

Returns the capability that must be used to end the pause. This is
either `resumeCapability`, or a new capability when `resumeCapability`
is omitted.

If [pauseCapability](pausecapability) is `null`, or it\'s not the pause
capability of the isolate identified by [controlPort](controlport), the
pause request is ignored by the receiving isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Capability pause([Capability? resumeCapability]) {
  resumeCapability ??= Capability();
  _pause(resumeCapability);
  return resumeCapability;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/pause.html>
:::
