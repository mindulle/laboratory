[dart:html](../../dart-html/dart-html-library){._links-link}

PresentationRequest constructor
===============================

::: {.section .multi-line-signature}
PresentationRequest(

1.  dynamic url\_OR\_urls

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory PresentationRequest(url_OR_urls) {
  if ((url_OR_urls is String)) {
    return PresentationRequest._create_1(url_OR_urls);
  }
  if ((url_OR_urls is List<String>)) {
    List urls_1 = convertDartToNative_StringArray(url_OR_urls);
    return PresentationRequest._create_2(urls_1);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PresentationRequest/PresentationRequest.html>
:::
