[dart:html](../../dart-html/dart-html-library){._links-link}

readyState property
===================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) readyState
:::

Indicator of the current state of the request:

  ------- ------------------ -----------------------------------------------------------------------
  Value   State              Meaning
  0       unsent             `open()` has not yet been called
  1       opened             `send()` has not yet been called
  2       headers received   `sent()` has been called; response headers and `status` are available
  3       loading            `responseText` holds some data
  4       done               request is complete
  ------- ------------------ -----------------------------------------------------------------------

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get readyState native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/readyState.html>
:::
