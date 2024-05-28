[dart:svg](../../dart-svg/dart-svg-library){._links-link}

onKeyDown property
==================

::: {#getter .section .multi-line-signature}
[ElementStream](../../dart-html/elementstream-class)\<[KeyboardEvent](../../dart-html/keyboardevent-class)\>
onKeyDown

::: {.features}
override
:::
:::

Stream of `keydown` events handled by this
[Element](../../dart-html/element-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<KeyboardEvent> get onKeyDown => keyDownEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/onKeyDown.html>
:::
