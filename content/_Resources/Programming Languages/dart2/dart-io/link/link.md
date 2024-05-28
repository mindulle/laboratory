[dart:io](../../dart-io/dart-io-library){._links-link}

Link constructor
================

::: {.section .multi-line-signature}
Link(

1.  [String](../../dart-core/string-class) path

)
:::

Creates a Link object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
factory Link(String path) {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return new _Link(path);
  }
  return overrides.createLink(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/Link.html>
:::
