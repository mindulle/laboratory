[dart:io](../../dart-io/dart-io-library){._links-link}

isWatchSupported property
=========================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isWatchSupported
:::

Test if [watch](watch) is supported on the current system.

OS X 10.6 and below is not supported.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get isWatchSupported {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return _FileSystemWatcher.isSupported;
  }
  return overrides.fsWatchIsSupported();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isWatchSupported.html>
:::
