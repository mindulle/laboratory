[dart:html](../../dart-html/dart-html-library){._links-link}

allowHtml5 method
=================

::: {.section .multi-line-signature}
void allowHtml5(

1.  {[UriPolicy](../uripolicy-class)? uriPolicy}

)
:::

Allow common safe HTML5 elements and attributes.

This list is based off of the Caja whitelists at:
<https://code.google.com/p/google-caja/wiki/CajaWhitelists>.

Common things which are not allowed are script elements, style
attributes and any script handlers.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowHtml5({UriPolicy? uriPolicy}) {
  add(new _Html5NodeValidator(uriPolicy: uriPolicy));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowHtml5.html>
:::
