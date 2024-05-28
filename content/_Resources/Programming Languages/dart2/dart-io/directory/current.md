[dart:io](../../dart-io/dart-io-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
[Directory](../directory-class) current
:::

Creates a directory object pointing to the current working directory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Directory get current {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return _Directory.current;
  }
  return overrides.getCurrentDirectory();
}
```

::: {#setter .section .multi-line-signature}
void current=(dynamic path)
:::

Sets the current working directory of the Dart process.

This affects all running isolates. The new value set can be either a
[Directory](../directory-class) or a
[String](../../dart-core/string-class).

The new value is passed to the OS\'s system call unchanged, so a
relative path passed as the new working directory will be resolved by
the OS.

Note that setting the current working directory is a synchronous
operation and that it changes the working directory of *all* isolates.

Use this with care --- especially when working with asynchronous
operations and multiple isolates. Changing the working directory, while
asynchronous operations are pending or when other isolates are working
with the file system, can lead to unexpected results.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void set current(path) {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    _Directory.current = path;
    return;
  }
  overrides.setCurrentDirectory(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/current.html>
:::
