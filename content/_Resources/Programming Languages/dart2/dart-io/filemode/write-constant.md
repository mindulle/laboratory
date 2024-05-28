[dart:io](../../dart-io/dart-io-library){._links-link}

write constant
==============

::: {.section .multi-line-signature}
[FileMode](../filemode-class) const write
:::

Mode for opening a file for reading and writing. The file is overwritten
if it already exists. The file is created if it does not already exist.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const write = const FileMode._internal(1);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileMode/write-constant.html>
:::
