[dart:io](../../dart-io/dart-io-library){._links-link}

operatingSystemVersion property
===============================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) operatingSystemVersion
:::

A string representing the version of the operating system or platform.

The format of this string will vary by operating system, platform and
version and is not suitable for parsing. For example: \"Linux
5.11.0-1018-gcp \#20\~20.04.2-Ubuntu SMP Fri Sep 3 01:01:37 UTC 2021\"
\"Version 14.5 (Build 18E182)\" \'\"Windows 10 Pro\" 10.0 (Build
19043)\'

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String get operatingSystemVersion => _operatingSystemVersion;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/operatingSystemVersion.html>
:::
