[dart:html](../../dart-html/dart-html-library){._links-link}

end method
==========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) end()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future end() => promiseToFuture(JS("", "#.end()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/VRSession/end.html>
:::
