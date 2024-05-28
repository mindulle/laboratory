[dart:io](../../dart-io/dart-io-library){._links-link}

exitCode property
=================

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[int](../../dart-core/int-class)\>
exitCode
:::

A `Future` which completes with the exit code of the process when the
process completes.

The handling of exit codes is platform specific.

On Linux and OS X a normal exit code will be a positive value in the
range `[0..255]`. If the process was terminated due to a signal the exit
code will be a negative value in the range `[-255..-1]`, where the
absolute value of the exit code is the signal number. For example, if a
process crashes due to a segmentation violation the exit code will be
-11, as the signal SIGSEGV has the number 11.

On Windows a process can report any 32-bit value as an exit code. When
returning the exit code this exit code is turned into a signed value.
Some special values are used to report termination due to some system
event. E.g. if a process crashes due to an access violation the 32-bit
exit code is `0xc0000005`, which will be returned as the negative number
`-1073741819`. To get the original 32-bit value use
`(0x100000000 + exitCode) & 0xffffffff`.

There is no guarantee that [stdout](stdout) and [stderr](stderr) have
finished reporting the buffered output of the process when the returned
future completes. To be sure that all output is captured, wait for the
done event on the streams.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<int> get exitCode;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Process/exitCode.html>
:::
