[dart:io](../../dart-io/dart-io-library){._links-link}

localHostname property
======================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) localHostname
:::

The local hostname for the system.

For example: \"mycomputer.corp.example.com\" \"mycomputer\"

Uses the platform
[`gethostname`](https://pubs.opengroup.org/onlinepubs/9699919799/functions/gethostname.html)
implementation.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String get localHostname => _localHostname;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/localHostname.html>
:::
