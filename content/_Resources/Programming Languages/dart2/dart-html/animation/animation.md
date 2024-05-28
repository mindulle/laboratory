[dart:html](../../dart-html/dart-html-library){._links-link}

Animation constructor
=====================

::: {.section .multi-line-signature}
Animation(

1.  \[[AnimationEffectReadOnly](../animationeffectreadonly-class)?
    effect,
2.  [AnimationTimeline](../animationtimeline-class)? timeline\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Animation(
    [AnimationEffectReadOnly? effect, AnimationTimeline? timeline]) {
  if (timeline != null) {
    return Animation._create_1(effect, timeline);
  }
  if (effect != null) {
    return Animation._create_2(effect);
  }
  return Animation._create_3();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Animation/Animation.html>
:::
