[dart:html](../../dart-html/dart-html-library){._links-link}

responseXml property
====================

::: {#getter .section .multi-line-signature}
[Document](../document-class)? responseXml

::: {.features}
\@JSName(\'responseXML\')
:::
:::

The request response, or null on failure.

The response is processed as `text/xml` stream, unless responseType =
\'document\' and the request is synchronous.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('responseXML')

/**
 * The request response, or null on failure.
 *
 * The response is processed as
 * `text/xml` stream, unless responseType = 'document' and the request is
 * synchronous.
 */

Document? get responseXml native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/responseXml.html>
:::
