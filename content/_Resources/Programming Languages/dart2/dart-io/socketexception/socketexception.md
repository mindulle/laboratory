[dart:io](../../dart-io/dart-io-library){._links-link}

SocketException constructor
===========================

::: {.section .multi-line-signature}
const SocketException(

1.  [String](../../dart-core/string-class) message,
2.  {[OSError](../oserror-class)? osError,
3.  [InternetAddress](../internetaddress-class)? address,
4.  [int](../../dart-core/int-class)? port}

)
:::

Creates a [SocketException](../socketexception-class) with the provided
values.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const SocketException(this.message, {this.osError, this.address, this.port});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketException/SocketException.html>
:::
