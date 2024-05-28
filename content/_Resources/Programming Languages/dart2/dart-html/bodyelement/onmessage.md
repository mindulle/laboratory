[dart:html](../../dart-html/dart-html-library){._links-link}

onMessage property
==================

::: {#getter .section .multi-line-signature}
[ElementStream](../elementstream-class)\<[MessageEvent](../messageevent-class)\>
onMessage

::: {.features}
override
:::
:::

Stream of `message` events handled by this
[BodyElement](../bodyelement-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<MessageEvent> get onMessage => messageEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BodyElement/onMessage.html>
:::
