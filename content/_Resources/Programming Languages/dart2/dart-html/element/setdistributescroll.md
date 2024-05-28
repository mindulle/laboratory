[dart:html](../../dart-html/dart-html-library){._links-link}

setDistributeScroll method
==========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[ScrollState](../scrollstate-class)\>
setDistributeScroll(

1.  [String](../../dart-core/string-class) nativeScrollBehavior

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<ScrollState> setDistributeScroll(String nativeScrollBehavior) {
  var completer = new Completer<ScrollState>();
  _setDistributeScroll((value) {
    completer.complete(value);
  }, nativeScrollBehavior);
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/setDistributeScroll.html>
:::
