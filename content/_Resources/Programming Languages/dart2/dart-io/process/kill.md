[dart:io](../../dart-io/dart-io-library){._links-link}

kill method
===========

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) kill(

1.  \[[ProcessSignal](../processsignal-class) signal =
    ProcessSignal.sigterm\]

)
:::

Kills the process.

Where possible, sends the `signal` to the process. This includes Linux
and OS X. The default signal is
[ProcessSignal.sigterm](../processsignal/sigterm-constant) which will
normally terminate the process.

On platforms without signal support, including Windows, the call just
terminates the process in a platform specific way, and the `signal`
parameter is ignored.

Returns `true` if the signal is successfully delivered to the process.
Otherwise the signal could not be sent, usually meaning that the process
is already dead.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool kill([ProcessSignal signal = ProcessSignal.sigterm]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Process/kill.html>
:::
