[dart:html](../../dart-html/dart-html-library){._links-link}

abort method
============

::: {.section .multi-line-signature}
void abort()
:::

Stop the current request.

The request can only be stopped if readyState is `HEADERS_RECEIVED` or
`LOADING`. If this method is not in the process of being sent, the
method has no effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void abort() native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/abort.html>
:::
