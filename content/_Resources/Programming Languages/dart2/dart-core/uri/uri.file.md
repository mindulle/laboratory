[dart:core](../../dart-core/dart-core-library){._links-link}

Uri.file constructor
====================

::: {.section .multi-line-signature}
Uri.file(

1.  [String](../string-class) path,
2.  {[bool](../bool-class)? windows}

)
:::

Creates a new file URI from an absolute or relative file path.

The file path is passed in `path`.

This path is interpreted using either Windows or non-Windows semantics.

With non-Windows semantics, the slash (`/`) is used to separate path
segments in the input `path`.

With Windows semantics, backslash (`\`) and forward-slash (`/`) are used
to separate path segments in the input `path`, except if the path starts
with `\\?\` in which case only backslash (`\`) separates path segments
in `path`.

If the path starts with a path separator, an absolute URI (with the
`file` scheme and an empty authority) is created. Otherwise a relative
URI reference with no scheme or authority is created. One exception to
this rule is that when Windows semantics is used and the path starts
with a drive letter followed by a colon (\":\") and a path separator,
then an absolute URI is created.

The default for whether to use Windows or non-Windows semantics is
determined from the platform Dart is running on. When running in the
standalone VM, this is detected by the VM based on the operating system.
When running in a browser, non-Windows semantics is always used.

To override the automatic detection of which semantics to use pass a
value for `windows`. Passing `true` will use Windows semantics and
passing `false` will use non-Windows semantics.

Examples using non-Windows semantics:

``` {.language-dart data-language="dart"}
// xxx/yyy
Uri.file('xxx/yyy', windows: false);

// xxx/yyy/
Uri.file('xxx/yyy/', windows: false);

// file:///xxx/yyy
Uri.file('/xxx/yyy', windows: false);

// file:///xxx/yyy/
Uri.file('/xxx/yyy/', windows: false);

// C%3A
Uri.file('C:', windows: false);
```

Examples using Windows semantics:

``` {.language-dart data-language="dart"}
// xxx/yyy
Uri.file(r'xxx\yyy', windows: true);

// xxx/yyy/
Uri.file(r'xxx\yyy\', windows: true);

file:///xxx/yyy
Uri.file(r'\xxx\yyy', windows: true);

file:///xxx/yyy/
Uri.file(r'\xxx\yyy/', windows: true);

// file:///C:/xxx/yyy
Uri.file(r'C:\xxx\yyy', windows: true);

// This throws an error. A path with a drive letter, but no following
// path, is not allowed.
Uri.file(r'C:', windows: true);

// This throws an error. A path with a drive letter is not absolute.
Uri.file(r'C:xxx\yyy', windows: true);

// file://server/share/file
Uri.file(r'\\server\share\file', windows: true);
```

If the path passed is not a valid file path, an error is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uri.file(String path, {bool? windows}) = _Uri.file;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/Uri.file.html>
:::
