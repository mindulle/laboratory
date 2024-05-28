[dart:html](../../dart-html/dart-html-library){._links-link}

caretRangeFromPoint method
==========================

::: {.section .multi-line-signature}
<div>

1.  \@Unstable()

</div>

[Range](../range-class) caretRangeFromPoint(

1.  [int](../../dart-core/int-class)? x,
2.  [int](../../dart-core/int-class)? y

)

::: {.features}
\@Unstable()
:::
:::

UNSTABLE: Chrome-only - create a Range from the given point.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Unstable()
Range caretRangeFromPoint(int? x, int? y) {
  return _caretRangeFromPoint(x, y);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HtmlDocument/caretRangeFromPoint.html>
:::
