[dart:io](../dart-io/dart-io-library){._links-link}

exitCode top-level property
===========================

::: {#getter .section .multi-line-signature}
[int](../dart-core/int-class) exitCode
:::

Get the global exit code for the Dart VM.

The exit code is global for the Dart VM and the last assignment to
exitCode from any isolate determines the exit code of the Dart VM on
normal termination.

See [exit](exit) for more information on how to chose a value for the
exit code.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get exitCode => _ProcessUtils._getExitCode();
```

::: {#setter .section .multi-line-signature}
void exitCode=([int](../dart-core/int-class) code)
:::

Set the global exit code for the Dart VM.

The exit code is global for the Dart VM and the last assignment to
exitCode from any isolate determines the exit code of the Dart VM on
normal termination.

Default value is `0`.

See [exit](exit) for more information on how to chose a value for the
exit code.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set exitCode(int code) {
  ArgumentError.checkNotNull(code, "code");
  _ProcessUtils._setExitCode(code);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/exitCode.html>
:::
