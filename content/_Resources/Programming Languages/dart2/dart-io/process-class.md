[dart:io](../dart-io/dart-io-library){._links-link}

Process class
=============

The means to execute a program.

Use the static [start](process/start) and [run](process/run) methods to
start a new process. The run method executes the process
non-interactively to completion. In contrast, the start method allows
your code to interact with the running process.

Start a process with the run method
-----------------------------------

The following code sample uses the run method to create a process that
runs the UNIX command `ls`, which lists the contents of a directory. The
run method completes with a [ProcessResult](processresult-class) object
when the process terminates. This provides access to the output and exit
code from the process. The run method does not return a `Process`
object; this prevents your code from interacting with the running
process.

``` {.language-dart data-language="dart"}
import 'dart:io';

main() async {
  // List all files in the current directory in UNIX-like systems.
  var result = await Process.run('ls', ['-l']);
  print(result.stdout);
}
```

Start a process with the start method
-------------------------------------

The following example uses start to create the process. The start method
returns a [Future](../dart-async/future-class) for a `Process` object.
When the future completes the process is started and your code can
interact with the process: writing to stdin, listening to stdout, and so
on.

The following sample starts the UNIX `cat` utility, which when given no
command-line arguments, echos its input. The program writes to the
process\'s standard input stream and prints data from its standard
output stream.

``` {.language-dart data-language="dart"}
import 'dart:io';
import 'dart:convert';

main() async {
  var process = await Process.start('cat', []);
  process.stdout
      .transform(utf8.decoder)
      .forEach(print);
  process.stdin.writeln('Hello, world!');
  process.stdin.writeln('Hello, galaxy!');
  process.stdin.writeln('Hello, universe!');
}
```

Standard I/O streams
--------------------

As seen in the previous code sample, you can interact with the
`Process`\'s standard output stream through the getter
[stdout](process/stdout), and you can interact with the `Process`\'s
standard input stream through the getter [stdin](process/stdin). In
addition, `Process` provides a getter [stderr](process/stderr) for using
the `Process`\'s standard error stream.

A `Process`\'s streams are distinct from the top-level streams for the
current program.

Exit codes
----------

Call the [exitCode](process/exitcode) method to get the exit code of the
process. The exit code indicates whether the program terminated
successfully (usually indicated with an exit code of 0) or with an
error.

If the start method is used, the [exitCode](process/exitcode) is
available through a future on the `Process` object (as shown in the
example below). If the run method is used, the
[exitCode](process/exitcode) is available through a getter on the
[ProcessResult](processresult-class) instance.

``` {.language-dart data-language="dart"}
import 'dart:io';

main() async {
  var process = await Process.start('ls', ['-l']);
  var exitCode = await process.exitCode;
  print('exit code: $exitCode');
}
```

Constructors
------------

[Process](process/process)()

Properties {#instance-properties}
----------

[exitCode](process/exitcode) →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

::: {.features}
read-only
:::

A `Future` which completes with the exit code of the process when the
process completes.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[pid](process/pid) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The process id of the process.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[stderr](process/stderr) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
read-only
:::

The standard error stream of the process as a `Stream`.

[stdin](process/stdin) → [IOSink](iosink-class)

::: {.features}
read-only
:::

The standard input stream of the process as an [IOSink](iosink-class).

[stdout](process/stdout) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
read-only
:::

The standard output stream of the process as a `Stream`.

Methods {#instance-methods}
-------

[kill](process/kill)(\[[ProcessSignal](processsignal-class) signal =
ProcessSignal.sigterm\]) → [bool](../dart-core/bool-class)

Kills the process.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[killPid](process/killpid)([int](../dart-core/int-class) pid, \[[ProcessSignal](processsignal-class) signal = ProcessSignal.sigterm\]) → [bool](../dart-core/bool-class)
:   Kills the process with id `pid`.

[run](process/run)([String](../dart-core/string-class) executable, [List](../dart-core/list-class)\<[String](../dart-core/string-class)\> arguments, {[String](../dart-core/string-class)? workingDirectory, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? environment, [bool](../dart-core/bool-class) includeParentEnvironment = true, [bool](../dart-core/bool-class) runInShell = false, [Encoding](../dart-convert/encoding-class)? stdoutEncoding = systemEncoding, [Encoding](../dart-convert/encoding-class)? stderrEncoding = systemEncoding}) → [Future](../dart-async/future-class)\<[ProcessResult](processresult-class)\>
:   Starts a process and runs it non-interactively to completion. The
    process run is `executable` with the specified `arguments`.

[runSync](process/runsync)([String](../dart-core/string-class) executable, [List](../dart-core/list-class)\<[String](../dart-core/string-class)\> arguments, {[String](../dart-core/string-class)? workingDirectory, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? environment, [bool](../dart-core/bool-class) includeParentEnvironment = true, [bool](../dart-core/bool-class) runInShell = false, [Encoding](../dart-convert/encoding-class)? stdoutEncoding = systemEncoding, [Encoding](../dart-convert/encoding-class)? stderrEncoding = systemEncoding}) → [ProcessResult](processresult-class)
:   Starts a process and runs it to completion. This is a synchronous
    call and will block until the child process terminates.

[start](process/start)([String](../dart-core/string-class) executable, [List](../dart-core/list-class)\<[String](../dart-core/string-class)\> arguments, {[String](../dart-core/string-class)? workingDirectory, [Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? environment, [bool](../dart-core/bool-class) includeParentEnvironment = true, [bool](../dart-core/bool-class) runInShell = false, [ProcessStartMode](processstartmode-class) mode = ProcessStartMode.normal}) → [Future](../dart-async/future-class)\<[Process](process-class)\>
:   Starts a process running the `executable` with the specified
    `arguments`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Process-class.html>
:::
