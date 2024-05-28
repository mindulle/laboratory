[dart:io](../../dart-io/dart-io-library){._links-link}

HttpClient constructor
======================

::: {.section .multi-line-signature}
HttpClient(

1.  {[SecurityContext](../securitycontext-class)? context}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HttpClient({SecurityContext? context}) {
  HttpOverrides? overrides = HttpOverrides.current;
  if (overrides == null) {
    return _HttpClient(context);
  }
  return overrides.createHttpClient(context);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/HttpClient.html>
:::
