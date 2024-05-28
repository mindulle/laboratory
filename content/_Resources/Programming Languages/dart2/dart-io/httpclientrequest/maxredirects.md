[dart:io](../../dart-io/dart-io-library){._links-link}

maxRedirects property
=====================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) maxRedirects

::: {.features}
read / write
:::
:::

Set this property to the maximum number of redirects to follow when
[followRedirects](followredirects) is `true`. If this number is exceeded
an error event will be added with a
[RedirectException](../redirectexception-class).

The default value is 5.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int maxRedirects = 5;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest/maxRedirects.html>
:::
