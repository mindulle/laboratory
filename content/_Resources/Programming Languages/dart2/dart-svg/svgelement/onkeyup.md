[dart:svg](../../dart-svg/dart-svg-library){._links-link}

onKeyUp property
================

::: {#getter .section .multi-line-signature}
[ElementStream](../../dart-html/elementstream-class)\<[KeyboardEvent](../../dart-html/keyboardevent-class)\>
onKeyUp

::: {.features}
override
:::
:::

Stream of `keyup` events handled by this
[Element](../../dart-html/element-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<KeyboardEvent> get onKeyUp => keyUpEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/onKeyUp.html>
:::
