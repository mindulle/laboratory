[dart:html](../../dart-html/dart-html-library){._links-link}

overrideMimeType method
=======================

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME)
2.  \@SupportedBrowser(SupportedBrowser.FIREFOX)
3.  \@SupportedBrowser(SupportedBrowser.SAFARI)

</div>

void overrideMimeType(

1.  [String](../../dart-core/string-class) mime

)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::
:::

Specify a particular MIME type (such as `text/xml`) desired for the
response.

This value must be set before the request has been sent. See also the
list of [IANA Official MIME
types](https://www.iana.org/assignments/media-types/media-types.xhtml).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
@SupportedBrowser(SupportedBrowser.SAFARI)
void overrideMimeType(String mime) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/overrideMimeType.html>
:::
