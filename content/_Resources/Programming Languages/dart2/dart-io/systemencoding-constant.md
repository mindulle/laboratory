[dart:io](../dart-io/dart-io-library){._links-link}

systemEncoding top-level constant
=================================

::: {.section .multi-line-signature}
[SystemEncoding](systemencoding-class) const systemEncoding
:::

The current system encoding.

This is used for converting from bytes to and from Strings when
communicating on stdin, stdout and stderr.

On Windows this will use the currently active code page for the
conversion. On all other systems it will always use UTF-8.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const SystemEncoding systemEncoding = const SystemEncoding();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/systemEncoding-constant.html>
:::
