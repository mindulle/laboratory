[dart:io](../../dart-io/dart-io-library){._links-link}

resolveSymbolicLinksSync method
===============================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) resolveSymbolicLinksSync()

::: {.features}
override
:::
:::

Resolves the path of a file system object relative to the current
working directory.

Resolves all symbolic links on the path and resolves all `..` and `.`
path segments.

[resolveSymbolicLinksSync](resolvesymboliclinkssync) uses the operating
system\'s native file system API to resolve the path, using the
`realpath` function on linux and OS X, and the
`GetFinalPathNameByHandle` function on Windows. If the path does not
point to an existing file system object, `resolveSymbolicLinksSync`
throws a `FileSystemException`.

On Windows the `..` segments are resolved *before* resolving the
symbolic link, and on other platforms the symbolic links are *resolved
to their target* before applying a `..` that follows.

To ensure the same behavior on all platforms resolve `..` segments
before calling `resolveSymbolicLinksSync`. One way of doing this is with
the [Uri](../../dart-core/uri-class) class:

``` {.language-dart data-language="dart"}
var path = Uri.parse('.').resolveUri(Uri.file(input)).toFilePath();
if (path == '') path = '.';
var resolved = File(path).resolveSymbolicLinksSync();
print(resolved);
```

since `Uri.resolve` removes `..` segments. This will result in the
Windows behavior.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String resolveSymbolicLinksSync();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/resolveSymbolicLinksSync.html>
:::
