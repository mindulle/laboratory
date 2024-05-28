[dart:html](../../dart-html/dart-html-library){._links-link}

WorkletAnimation constructor
============================

::: {.section .multi-line-signature}
WorkletAnimation(

1.  [String](../../dart-core/string-class) animatorName,
2.  [List](../../dart-core/list-class)\<[KeyframeEffectReadOnly](../keyframeeffectreadonly-class)\>
    effects,
3.  [List](../../dart-core/list-class)\<[Object](../../dart-core/object-class)\>
    timelines,
4.  dynamic options

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory WorkletAnimation(
    String animatorName,
    List<KeyframeEffectReadOnly> effects,
    List<Object> timelines,
    /*SerializedScriptValue*/ options) {
  var options_1 = convertDartToNative_SerializedScriptValue(options);
  return WorkletAnimation._create_1(
      animatorName, effects, timelines, options_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WorkletAnimation/WorkletAnimation.html>
:::
