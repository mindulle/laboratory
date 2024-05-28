[dart:html](../../dart-html/dart-html-library){._links-link}

send method
===========

::: {.section .multi-line-signature}
void send(

1.  \[dynamic body\_OR\_data\]

)
:::

Send the request with any given `data`.

Note: Most simple HTTP requests can be accomplished using the
[getString](getstring), [request](request),
[requestCrossOrigin](requestcrossorigin), or
[postFormData](postformdata) methods. Use of this `send` method is
intended only for more complex HTTP requests where finer-grained control
is needed.

Other resources
---------------

-   [XMLHttpRequest.send](https://developer.mozilla.org/en-US/docs/DOM/XMLHttpRequest#send%28%29)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void send([body_OR_data]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/send.html>
:::
