[dart:io](../../dart-io/dart-io-library){._links-link}

parentOf method
===============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) parentOf(

1.  [String](../../dart-core/string-class) path

)
:::

The parent path of a path.

Finds the final path component of a path, using the platform\'s path
separator to split the path, and returns the prefix up to that part.

Will not remove the root component of a Windows path, like \"C:\\\" or
\"\\\\server\_name\\\". Includes a trailing path separator in the last
part of `path`, and leaves no trailing path separator.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String parentOf(String path) {
  int rootEnd = -1;
  if (Platform.isWindows) {
    if (path.startsWith(_absoluteWindowsPathPattern)) {
      // Root ends at first / or \ after the first two characters.
      rootEnd = path.indexOf(new RegExp(r'[/\\]'), 2);
      if (rootEnd == -1) return path;
    } else if (path.startsWith('\\') || path.startsWith('/')) {
      rootEnd = 0;
    }
  } else if (path.startsWith('/')) {
    rootEnd = 0;
  }
  // Ignore trailing slashes.
  // All non-trivial cases have separators between two non-separators.
  int pos = path.lastIndexOf(_parentRegExp);
  if (pos > rootEnd) {
    return path.substring(0, pos + 1);
  } else if (rootEnd > -1) {
    return path.substring(0, rootEnd + 1);
  } else {
    return '.';
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/parentOf.html>
:::
