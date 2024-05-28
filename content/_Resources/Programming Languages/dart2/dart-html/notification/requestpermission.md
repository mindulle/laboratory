[dart:html](../../dart-html/dart-html-library){._links-link}

requestPermission method
========================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'requestPermission\')

</div>

[Future](../../dart-async/future-class)\<[String](../../dart-core/string-class)\>
requestPermission()

::: {.features}
\@JSName(\'requestPermission\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('requestPermission')
static Future<String> requestPermission() {
  var completer = new Completer<String>();
  _requestPermission((value) {
    completer.complete(value);
  });
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Notification/requestPermission.html>
:::
