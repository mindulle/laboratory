[dart:io](../dart-io/dart-io-library){._links-link}

exit function
=============

::: {.section .multi-line-signature}
Never exit(

1.  [int](../dart-core/int-class) code

)
:::

Exit the Dart VM process immediately with the given exit code.

This does not wait for any asynchronous operations to terminate nor
execute `finally` blocks. Using [exit](exit) is therefore very likely to
lose data.

While debugging, the VM will not respect the `--pause-isolates-on-exit`
flag if [exit](exit) is called as invoking this method causes the Dart
VM process to shutdown immediately. To properly break on exit, consider
calling [debugger](../dart-developer/debugger) from `dart:developer` or
[Isolate.pause](../dart-isolate/isolate/pause) from `dart:isolate` on
[Isolate.current](../dart-isolate/isolate/current) to pause the isolate
before invoking [exit](exit).

The handling of exit codes is platform specific.

On Linux and OS X an exit code for normal termination will always be in
the range `[0..255]`. If an exit code outside this range is set the
actual exit code will be the lower 8 bits masked off and treated as an
unsigned value. E.g. using an exit code of -1 will result in an actual
exit code of 255 being reported.

On Windows the exit code can be set to any 32-bit value. However some of
these values are reserved for reporting system errors like crashes.

Besides this the Dart executable itself uses an exit code of `254` for
reporting compile time errors and an exit code of `255` for reporting
runtime error (unhandled exception).

Due to these facts it is recommended to only use exit codes in the range
\[0..127\] for communicating the result of running a Dart program to the
surrounding environment. This will avoid any cross-platform issues.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Never exit(int code) {
  ArgumentError.checkNotNull(code, "code");
  if (!_EmbedderConfig._mayExit) {
    throw new UnsupportedError(
        "This embedder disallows calling dart:io's exit()");
  }
  _ProcessUtils._exit(code);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/exit.html>
:::
