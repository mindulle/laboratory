[dart:html](../../dart-html/dart-html-library){._links-link}

Path2D constructor
==================

::: {.section .multi-line-signature}
Path2D(

1.  \[dynamic path\_OR\_text\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Path2D([path_OR_text]) {
  if (path_OR_text == null) {
    return Path2D._create_1();
  }
  if ((path_OR_text is Path2D)) {
    return Path2D._create_2(path_OR_text);
  }
  if ((path_OR_text is String)) {
    return Path2D._create_3(path_OR_text);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Path2D/Path2D.html>
:::
