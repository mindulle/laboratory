[dart:html](../../dart-html/dart-html-library){._links-link}

allowImages method
==================

::: {.section .multi-line-signature}
void allowImages(

1.  \[[UriPolicy](../uripolicy-class)? uriPolicy\]

)
:::

Allows image elements.

The UriPolicy can be used to restrict the locations the images may be
loaded from. By default this will use the default
[UriPolicy](../uripolicy-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowImages([UriPolicy? uriPolicy]) {
  if (uriPolicy == null) {
    uriPolicy = new UriPolicy();
  }
  add(new _SimpleNodeValidator.allowImages(uriPolicy));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowImages.html>
:::
