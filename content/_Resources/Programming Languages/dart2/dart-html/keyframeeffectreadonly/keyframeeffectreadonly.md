[dart:html](../../dart-html/dart-html-library){._links-link}

KeyframeEffectReadOnly constructor
==================================

::: {.section .multi-line-signature}
KeyframeEffectReadOnly(

1.  [Element](../element-class)? target,
2.  [Object](../../dart-core/object-class)? effect,
3.  \[[Object](../../dart-core/object-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory KeyframeEffectReadOnly(Element? target, Object? effect,
    [Object? options]) {
  if (options != null) {
    return KeyframeEffectReadOnly._create_1(target, effect, options);
  }
  return KeyframeEffectReadOnly._create_2(target, effect);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyframeEffectReadOnly/KeyframeEffectReadOnly.html>
:::
