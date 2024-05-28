[dart:io](../../dart-io/dart-io-library){._links-link}

addProxyCredentials method
==========================

::: {.section .multi-line-signature}
void addProxyCredentials(

1.  [String](../../dart-core/string-class) host,
2.  [int](../../dart-core/int-class) port,
3.  [String](../../dart-core/string-class) realm,
4.  [HttpClientCredentials](../httpclientcredentials-class) credentials

)
:::

Add credentials to be used for authorizing HTTP proxies.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addProxyCredentials(
    String host, int port, String realm, HttpClientCredentials credentials);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/addProxyCredentials.html>
:::
