[dart:io](../../dart-io/dart-io-library){._links-link}

reasonPhrase property
=====================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) reasonPhrase

::: {.features}
read / write
:::
:::

The reason phrase for the response.

If no reason phrase is explicitly set, a default reason phrase is
provided.

The reason phrase must be set before the body is written to. Setting the
reason phrase after writing to the response body or closing the response
will throw a [StateError](../../dart-core/stateerror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
late String reasonPhrase;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpResponse/reasonPhrase.html>
:::
