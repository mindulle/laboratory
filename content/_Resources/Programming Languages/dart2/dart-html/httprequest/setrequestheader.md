[dart:html](../../dart-html/dart-html-library){._links-link}

setRequestHeader method
=======================

::: {.section .multi-line-signature}
void setRequestHeader(

1.  [String](../../dart-core/string-class) name,
2.  [String](../../dart-core/string-class) value

)
:::

Sets the value of an HTTP request header.

This method should be called after the request is opened, but before the
request is sent.

Multiple calls with the same header will combine all their values into a
single header.

Other resources
---------------

-   [XMLHttpRequest.setRequestHeader](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest#setRequestHeader())
    from MDN.
-   [The setRequestHeader()
    method](http://www.w3.org/TR/XMLHttpRequest/#the-setrequestheader()-method)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setRequestHeader(String name, String value) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/setRequestHeader.html>
:::
