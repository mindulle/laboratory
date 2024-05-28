[dart:io](../../dart-io/dart-io-library){._links-link}

systemTemp property
===================

::: {#getter .section .multi-line-signature}
[Directory](../directory-class) systemTemp
:::

The system temp directory.

This is the directory provided by the operating system for creating
temporary files and directories in. The location of the system temporary
directory is platform-dependent, and may be controlled by an environment
variable on some platforms.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Directory get systemTemp {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return _Directory.systemTemp;
  }
  return overrides.getSystemTempDirectory();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/systemTemp.html>
:::
