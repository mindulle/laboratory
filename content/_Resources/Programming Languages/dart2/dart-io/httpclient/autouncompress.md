[dart:io](../../dart-io/dart-io-library){._links-link}

autoUncompress property
=======================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) autoUncompress

::: {.features}
read / write
:::
:::

Gets and sets whether the body of a response will be automatically
uncompressed.

The body of an HTTP response can be compressed. In most situations
providing the un-compressed body is most convenient. Therefore the
default behavior is to un-compress the body. However in some situations
(e.g. implementing a transparent proxy) keeping the uncompressed stream
is required.

NOTE: Headers in the response are never modified. This means that when
automatic un-compression is turned on the value of the header
`Content-Length` will reflect the length of the original compressed
body. Likewise the header `Content-Encoding` will also have the original
value indicating compression.

NOTE: Automatic un-compression is only performed if the
`Content-Encoding` header value is `gzip`.

This value affects all responses produced by this client after the value
is changed.

To disable, set to `false`.

Default is `true`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool autoUncompress = true;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/autoUncompress.html>
:::
