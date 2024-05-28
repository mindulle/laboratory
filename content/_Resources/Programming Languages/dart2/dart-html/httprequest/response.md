[dart:html](../../dart-html/dart-html-library){._links-link}

response property
=================

::: {#getter .section .multi-line-signature}
dynamic response

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\'),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::
:::

The data received as a reponse from the request.

The data could be in the form of a
[String](../../dart-core/string-class),
[ByteBuffer](../../dart-typed_data/bytebuffer-class),
[Document](../document-class), [Blob](../blob-class), or json (also a
[String](../../dart-core/string-class)). `null` indicates request
failure.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
@SupportedBrowser(SupportedBrowser.IE, '10')
@SupportedBrowser(SupportedBrowser.SAFARI)
dynamic get response => _convertNativeToDart_XHR_Response(this._get_response);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/response.html>
:::
