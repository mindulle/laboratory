[dart:html](../../dart-html/dart-html-library){._links-link}

onKeyPress property
===================

::: {#getter .section .multi-line-signature}
[ElementStream](../elementstream-class)\<[KeyboardEvent](../keyboardevent-class)\>
onKeyPress

::: {.features}
override
:::
:::

Stream of `keypress` events handled by this [Element](../element-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<KeyboardEvent> get onKeyPress => keyPressEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/onKeyPress.html>
:::
