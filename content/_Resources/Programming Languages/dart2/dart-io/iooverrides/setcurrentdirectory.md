[dart:io](../../dart-io/dart-io-library){._links-link}

setCurrentDirectory method
==========================

::: {.section .multi-line-signature}
void setCurrentDirectory(

1.  [String](../../dart-core/string-class) path

)
:::

Sets the current working directory to be `path`.

When this override is installed, this function overrides the behavior of
the setter `Directory.current`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setCurrentDirectory(String path) {
  _Directory.current = path;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/setCurrentDirectory.html>
:::
