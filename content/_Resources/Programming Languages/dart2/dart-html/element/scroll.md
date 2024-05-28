[dart:html](../../dart-html/dart-html-library){._links-link}

scroll method
=============

::: {.section .multi-line-signature}
void scroll(

1.  \[dynamic options\_OR\_x,
2.  [num](../../dart-core/num-class)? y\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void scroll([options_OR_x, num? y]) {
  if (options_OR_x == null && y == null) {
    _scroll_1();
    return;
  }
  if ((options_OR_x is Map) && y == null) {
    var options_1 = convertDartToNative_Dictionary(options_OR_x);
    _scroll_2(options_1);
    return;
  }
  if (y != null && (options_OR_x is num)) {
    _scroll_3(options_OR_x, y);
    return;
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/scroll.html>
:::
