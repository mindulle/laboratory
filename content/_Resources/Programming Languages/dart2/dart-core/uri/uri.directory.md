[dart:core](../../dart-core/dart-core-library){._links-link}

Uri.directory constructor
=========================

::: {.section .multi-line-signature}
Uri.directory(

1.  [String](../string-class) path,
2.  {[bool](../bool-class)? windows}

)
:::

Like [Uri.file](uri.file) except that a non-empty URI path ends in a
slash.

If `path` is not empty, and it doesn\'t end in a directory separator,
then a slash is added to the returned URI\'s path. In all other cases,
the result is the same as returned by `Uri.file`.

Example:

``` {.language-dart data-language="dart"}
final fileDirectory = Uri.directory('data/images', windows: false);
print(fileDirectory); // data/images/

final fileDirectoryWindows =
   Uri.directory(r'C:\data\images', windows: true);
print(fileDirectoryWindows); // file:///C:/data/images/
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uri.directory(String path, {bool? windows}) = _Uri.directory;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/Uri.directory.html>
:::
