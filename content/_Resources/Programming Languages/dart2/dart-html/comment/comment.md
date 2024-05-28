[dart:html](../../dart-html/dart-html-library){._links-link}

Comment constructor
===================

::: {.section .multi-line-signature}
Comment(

1.  \[[String](../../dart-core/string-class)? data\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Comment([String? data]) {
  return JS('returns:Comment;depends:none;effects:none;new:true',
      '#.createComment(#)', document, data == null ? "" : data);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Comment/Comment.html>
:::
