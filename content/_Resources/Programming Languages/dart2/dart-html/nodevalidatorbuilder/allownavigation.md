[dart:html](../../dart-html/dart-html-library){._links-link}

allowNavigation method
======================

::: {.section .multi-line-signature}
void allowNavigation(

1.  \[[UriPolicy](../uripolicy-class)? uriPolicy\]

)
:::

Allows navigation elements- Form and Anchor tags, along with common
attributes.

The UriPolicy can be used to restrict the locations the navigation
elements are allowed to direct to. By default this will use the default
[UriPolicy](../uripolicy-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowNavigation([UriPolicy? uriPolicy]) {
  if (uriPolicy == null) {
    uriPolicy = new UriPolicy();
  }
  add(new _SimpleNodeValidator.allowNavigation(uriPolicy));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowNavigation.html>
:::
