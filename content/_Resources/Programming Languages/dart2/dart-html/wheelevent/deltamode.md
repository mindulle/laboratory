[dart:html](../../dart-html/dart-html-library){._links-link}

deltaMode property
==================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) deltaMode
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get deltaMode {
  if (JS('bool', '!!(#.deltaMode)', this)) {
    return JS('int', '#.deltaMode', this);
  }
  // If not available then we're poly-filling and doing pixel scroll.
  return 0;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WheelEvent/deltaMode.html>
:::
