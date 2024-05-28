[dart:html](../../dart-html/dart-html-library){._links-link}

allowInlineStyles method
========================

::: {.section .multi-line-signature}
void allowInlineStyles(

1.  {[String](../../dart-core/string-class)? tagName}

)
:::

Allow inline styles on elements.

If `tagName` is not specified then this allows inline styles on all
elements. Otherwise tagName limits the styles to the specified elements.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowInlineStyles({String? tagName}) {
  if (tagName == null) {
    tagName = '*';
  } else {
    tagName = tagName.toUpperCase();
  }
  add(new _SimpleNodeValidator(null, allowedAttributes: ['$tagName::style']));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowInlineStyles.html>
:::
