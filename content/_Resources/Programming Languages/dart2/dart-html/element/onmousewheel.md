[dart:html](../../dart-html/dart-html-library){._links-link}

onMouseWheel property
=====================

::: {#getter .section .multi-line-signature}
[ElementStream](../elementstream-class)\<[WheelEvent](../wheelevent-class)\>
onMouseWheel

::: {.features}
override
:::
:::

Stream of `mousewheel` events handled by this
[Element](../element-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<WheelEvent> get onMouseWheel =>
    mouseWheelEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/onMouseWheel.html>
:::
