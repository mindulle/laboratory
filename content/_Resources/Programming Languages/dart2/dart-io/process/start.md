[dart:io](../../dart-io/dart-io-library){._links-link}

start method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Process](../process-class)\>
start(

1.  [String](../../dart-core/string-class) executable,
2.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    arguments,
3.  {[String](../../dart-core/string-class)? workingDirectory,
4.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\>? environment,
5.  [bool](../../dart-core/bool-class) includeParentEnvironment = true,
6.  [bool](../../dart-core/bool-class) runInShell = false,
7.  [ProcessStartMode](../processstartmode-class) mode =
    ProcessStartMode.normal}

)
:::

Starts a process running the `executable` with the specified
`arguments`.

Returns a `Future<Process>` that completes with a `Process` instance
when the process has been successfully started. That `Process` object
can be used to interact with the process. If the process cannot be
started the returned [Future](../../dart-async/future-class) completes
with an exception.

Use `workingDirectory` to set the working directory for the process.
Note that the change of directory occurs before executing the process on
some platforms, which may have impact when using relative paths for the
executable and the arguments.

Use `environment` to set the environment variables for the process. If
not set the environment of the parent process is inherited. Currently,
only US-ASCII environment variables are supported and errors are likely
to occur if an environment variable with code-points outside the
US-ASCII range is passed in.

If `includeParentEnvironment` is `true`, the process\'s environment will
include the parent process\'s environment, with `environment` taking
precedence. Default is `true`.

If `runInShell` is `true`, the process will be spawned through a system
shell. On Linux and OS X, `/bin/sh` is used, while
`%WINDIR%\system32\cmd.exe` is used on Windows.

Users must read all data coming on the [stdout](stdout) and
[stderr](stderr) streams of processes started with `Process.start`. If
the user does not read all data on the streams the underlying system
resources will not be released since there is still pending data.

The following code uses `Process.start` to grep for `main` in the file
`test.dart` on Linux.

``` {.language-dart data-language="dart"}
var process = await Process.start('grep', ['-i', 'main', 'test.dart']);
stdout.addStream(process.stdout);
stderr.addStream(process.stderr);
```

If `mode` is
[ProcessStartMode.normal](../processstartmode/normal-constant) (the
default) a child process will be started with `stdin`, `stdout` and
`stderr` connected.

If `mode` is
[ProcessStartMode.detached](../processstartmode/detached-constant) a
detached process will be created. A detached process has no connection
to its parent, and can keep running on its own when the parent dies. The
only information available from a detached process is its `pid`. There
is no connection to its `stdin`, `stdout` or `stderr`, nor will the
process\' exit code become available when it terminates.

If `mode` is
[ProcessStartMode.detachedWithStdio](../processstartmode/detachedwithstdio-constant)
a detached process will be created where the `stdin`, `stdout` and
`stderr` are connected. The creator can communicate with the child
through these. The detached process will keep running even if these
communication channels are closed. The process\' exit code will not
become available when it terminated.

The default value for `mode` is `ProcessStartMode.normal`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<Process> start(
    String executable, List<String> arguments,
    {String? workingDirectory,
    Map<String, String>? environment,
    bool includeParentEnvironment = true,
    bool runInShell = false,
    ProcessStartMode mode = ProcessStartMode.normal});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Process/start.html>
:::
