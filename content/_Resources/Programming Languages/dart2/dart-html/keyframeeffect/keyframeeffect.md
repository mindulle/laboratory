[dart:html](../../dart-html/dart-html-library){._links-link}

KeyframeEffect constructor
==========================

::: {.section .multi-line-signature}
KeyframeEffect(

1.  [Element](../element-class)? target,
2.  [Object](../../dart-core/object-class)? effect,
3.  \[[Object](../../dart-core/object-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory KeyframeEffect(Element? target, Object? effect, [Object? options]) {
  if (options != null) {
    return KeyframeEffect._create_1(target, effect, options);
  }
  return KeyframeEffect._create_2(target, effect);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyframeEffect/KeyframeEffect.html>
:::
