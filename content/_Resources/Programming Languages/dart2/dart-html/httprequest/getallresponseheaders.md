[dart:html](../../dart-html/dart-html-library){._links-link}

getAllResponseHeaders method
============================

::: {.section .multi-line-signature}
<div>

1.  \@Unstable()

</div>

[String](../../dart-core/string-class) getAllResponseHeaders()

::: {.features}
\@Unstable()
:::
:::

Retrieve all the response headers from a request.

`null` if no headers have been received. For multipart requests,
`getAllResponseHeaders` will return the response headers for the current
part of the request.

See also [HTTP response
headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Response_fields)
for a list of common response headers.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Unstable()
String getAllResponseHeaders() native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/getAllResponseHeaders.html>
:::
