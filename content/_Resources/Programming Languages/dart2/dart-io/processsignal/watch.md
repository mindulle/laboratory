[dart:io](../../dart-io/dart-io-library){._links-link}

watch method
============

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[ProcessSignal](../processsignal-class)\>
watch()
:::

Watch for process signals.

The following `ProcessSignal`s can be listened to:

-   [ProcessSignal.sighup](sighup-constant).
-   [ProcessSignal.sigint](sigint-constant). Signal sent by e.g. CTRL-C.
-   [ProcessSignal.sigterm](sigterm-constant). Not available on Windows.
-   [ProcessSignal.sigusr1](sigusr1-constant). Not available on Windows.
-   [ProcessSignal.sigusr2](sigusr2-constant). Not available on Windows.
-   [ProcessSignal.sigwinch](sigwinch-constant). Not available on
    Windows.

Other signals are disallowed, as they may be used by the VM.

A signal can be watched multiple times, from multiple isolates, where
all callbacks are invoked when signaled, in no specific order.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<ProcessSignal> watch() => _ProcessUtils._watchSignal(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessSignal/watch.html>
:::
