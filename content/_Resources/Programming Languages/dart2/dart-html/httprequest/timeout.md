[dart:html](../../dart-html/dart-html-library){._links-link}

timeout property
================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class)? timeout
:::

Length of time in milliseconds before a request is automatically
terminated.

When the time has passed, a
[HttpRequestEventTarget.timeoutEvent](../httprequesteventtarget/timeoutevent-constant)
is dispatched.

If [timeout](timeout) is set to 0, then the request will not time out.

Other resources
---------------

-   [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest#xmlhttprequest-timeout)
    from MDN.
-   [The timeout
    attribute](http://www.w3.org/TR/XMLHttpRequest/#the-timeout-attribute)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int? get timeout native;
```

::: {#setter .section .multi-line-signature}
void timeout=([int](../../dart-core/int-class)? value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set timeout(int? value) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/timeout.html>
:::
