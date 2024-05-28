[dart:io](../../dart-io/dart-io-library){._links-link}

redirects property
==================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[RedirectInfo](../redirectinfo-class)\>
redirects
:::

Returns the series of redirects this connection has been through. The
list will be empty if no redirects were followed. [redirects](redirects)
will be updated both in the case of an automatic and a manual redirect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<RedirectInfo> get redirects;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/redirects.html>
:::
