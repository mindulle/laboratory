[dart:html](../../dart-html/dart-html-library){._links-link}

getResponseHeader method
========================

::: {.section .multi-line-signature}
<div>

1.  \@Unstable()

</div>

[String](../../dart-core/string-class)? getResponseHeader(

1.  [String](../../dart-core/string-class) name

)

::: {.features}
\@Unstable()
:::
:::

Return the response header named `header`, or null if not found.

See also [HTTP response
headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Response_fields)
for a list of common response headers.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Unstable()
String? getResponseHeader(String name) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/getResponseHeader.html>
:::
