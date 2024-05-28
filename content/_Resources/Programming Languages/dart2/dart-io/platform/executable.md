[dart:io](../../dart-io/dart-io-library){._links-link}

executable property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) executable
:::

The path of the executable used to run the script in this isolate.
Usually `dart` when running on the Dart VM or the compiled script name
(`script_name.exe`).

The literal path used to identify the executable. This path might be
relative or just be a name from which the executable was found by
searching the system path.

Use [resolvedExecutable](resolvedexecutable) to get an absolute path to
the executable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String get executable => _Platform.executable;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/executable.html>
:::
