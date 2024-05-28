[dart:io](../../dart-io/dart-io-library){._links-link}

fsWatchIsSupported method
=========================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) fsWatchIsSupported()
:::

Returns `true` when [FileSystemEntity.watch](../filesystementity/watch)
is supported.

When this override is installed, this function overrides the behavior of
`FileSystemEntity.isWatchSupported`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool fsWatchIsSupported() => _FileSystemWatcher.isSupported;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/fsWatchIsSupported.html>
:::
