[dart:io](../../dart-io/dart-io-library){._links-link}

runSync method
==============

::: {.section .multi-line-signature}
[ProcessResult](../processresult-class) runSync(

1.  [String](../../dart-core/string-class) executable,
2.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    arguments,
3.  {[String](../../dart-core/string-class)? workingDirectory,
4.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\>? environment,
5.  [bool](../../dart-core/bool-class) includeParentEnvironment = true,
6.  [bool](../../dart-core/bool-class) runInShell = false,
7.  [Encoding](../../dart-convert/encoding-class)? stdoutEncoding =
    systemEncoding,
8.  [Encoding](../../dart-convert/encoding-class)? stderrEncoding =
    systemEncoding}

)
:::

Starts a process and runs it to completion. This is a synchronous call
and will block until the child process terminates.

The arguments are the same as for [Process.run](run).

Returns a [ProcessResult](../processresult-class) with the result of
running the process, i.e., exit code, standard out and standard in.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static ProcessResult runSync(
    String executable, List<String> arguments,
    {String? workingDirectory,
    Map<String, String>? environment,
    bool includeParentEnvironment = true,
    bool runInShell = false,
    Encoding? stdoutEncoding = systemEncoding,
    Encoding? stderrEncoding = systemEncoding});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Process/runSync.html>
:::
