[dart:core](../../dart-core/dart-core-library){._links-link}

toFilePath method
=================

::: {.section .multi-line-signature}
[String](../string-class) toFilePath(

1.  {[bool](../bool-class)? windows}

)
:::

Creates a file path from a file URI.

The returned path has either Windows or non-Windows semantics.

For non-Windows semantics, the slash (\"/\") is used to separate path
segments.

For Windows semantics, the backslash (\"\\\") separator is used to
separate path segments.

If the URI is absolute, the path starts with a path separator unless
Windows semantics is used and the first path segment is a drive letter.
When Windows semantics is used, a host component in the uri in
interpreted as a file server and a UNC path is returned.

The default for whether to use Windows or non-Windows semantics is
determined from the platform Dart is running on. When running in the
standalone VM, this is detected by the VM based on the operating system.
When running in a browser, non-Windows semantics is always used.

To override the automatic detection of which semantics to use pass a
value for `windows`. Passing `true` will use Windows semantics and
passing `false` will use non-Windows semantics.

If the URI ends with a slash (i.e. the last path component is empty),
the returned file path will also end with a slash.

With Windows semantics, URIs starting with a drive letter cannot be
relative to the current drive on the designated drive. That is, for the
URI `file:///c:abc` calling `toFilePath` will throw as a path segment
cannot contain colon on Windows.

Examples using non-Windows semantics (resulting of calling toFilePath in
comment):

``` {.language-dart data-language="dart"}
Uri.parse("xxx/yyy");  // xxx/yyy
Uri.parse("xxx/yyy/");  // xxx/yyy/
Uri.parse("file:///xxx/yyy");  // /xxx/yyy
Uri.parse("file:///xxx/yyy/");  // /xxx/yyy/
Uri.parse("file:///C:");  // /C:
Uri.parse("file:///C:a");  // /C:a
```

Examples using Windows semantics (resulting URI in comment):

``` {.language-dart data-language="dart"}
Uri.parse("xxx/yyy");  // xxx\yyy
Uri.parse("xxx/yyy/");  // xxx\yyy\
Uri.parse("file:///xxx/yyy");  // \xxx\yyy
Uri.parse("file:///xxx/yyy/");  // \xxx\yyy\
Uri.parse("file:///C:/xxx/yyy");  // C:\xxx\yyy
Uri.parse("file:C:xxx/yyy");  // Throws as a path segment
                              // cannot contain colon on Windows.
Uri.parse("file://server/share/file");  // \\server\share\file
```

If the URI is not a file URI, calling this throws
[UnsupportedError](../unsupportederror-class).

If the URI cannot be converted to a file path, calling this throws
[UnsupportedError](../unsupportederror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO(lrn): Deprecate and move functionality to File class or similar.
// The core libraries should not worry about the platform.
String toFilePath({bool? windows});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/toFilePath.html>
:::
