[dart:io](../../dart-io/dart-io-library){._links-link}

resolveSymbolicLinks method
===========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[String](../../dart-core/string-class)\>
resolveSymbolicLinks()

::: {.features}
override
:::
:::

Resolves the path of a file system object relative to the current
working directory.

Resolves all symbolic links on the path and resolves all `..` and `.`
path segments.

[resolveSymbolicLinks](resolvesymboliclinks) uses the operating
system\'s native file system API to resolve the path, using the
`realpath` function on Linux and OS X, and the
`GetFinalPathNameByHandle` function on Windows. If the path does not
point to an existing file system object, `resolveSymbolicLinks` throws a
`FileSystemException`.

On Windows the `..` segments are resolved *before* resolving the
symbolic link, and on other platforms the symbolic links are *resolved
to their target* before applying a `..` that follows.

To ensure the same behavior on all platforms resolve `..` segments
before calling `resolveSymbolicLinks`. One way of doing this is with the
[Uri](../../dart-core/uri-class) class:

``` {.language-dart data-language="dart"}
var path = Uri.parse('.').resolveUri(Uri.file(input)).toFilePath();
if (path == '') path = '.';
var resolved = await File(path).resolveSymbolicLinks();
print(resolved);
```

since `Uri.resolve` removes `..` segments. This will result in the
Windows behavior.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<String> resolveSymbolicLinks();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/resolveSymbolicLinks.html>
:::
