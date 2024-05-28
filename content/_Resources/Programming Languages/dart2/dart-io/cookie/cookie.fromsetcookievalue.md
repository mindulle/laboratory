[dart:io](../../dart-io/dart-io-library){._links-link}

Cookie.fromSetCookieValue constructor
=====================================

::: {.section .multi-line-signature}
Cookie.fromSetCookieValue(

1.  [String](../../dart-core/string-class) value

)
:::

Creates a new cookie by parsing a header value from a \'set-cookie\'
header.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Cookie.fromSetCookieValue(String value) {
  return _Cookie.fromSetCookieValue(value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Cookie/Cookie.fromSetCookieValue.html>
:::
