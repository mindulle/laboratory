[dart:io](../../dart-io/dart-io-library){._links-link}

createHttpClient method
=======================

::: {.section .multi-line-signature}
[HttpClient](../httpclient-class) createHttpClient(

1.  [SecurityContext](../securitycontext-class)? context

)
:::

Returns a new [HttpClient](../httpclient-class) using the given
`context`.

When this override is installed, this function overrides the behavior of
`new HttpClient`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
HttpClient createHttpClient(SecurityContext? context) {
  return _HttpClient(context);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpOverrides/createHttpClient.html>
:::
