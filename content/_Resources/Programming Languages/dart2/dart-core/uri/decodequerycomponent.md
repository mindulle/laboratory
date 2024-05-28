[dart:core](../../dart-core/dart-core-library){._links-link}

decodeQueryComponent method
===========================

::: {.section .multi-line-signature}
[String](../string-class) decodeQueryComponent(

1.  [String](../string-class) encodedComponent,
2.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Decodes the percent-encoding in `encodedComponent`, converting pluses to
spaces.

It will create a byte-list of the decoded characters, and then use
`encoding` to decode the byte-list to a String. The default encoding is
UTF-8.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String decodeQueryComponent(String encodedComponent,
    {Encoding encoding = utf8}) {
  return _Uri._uriDecode(
      encodedComponent, 0, encodedComponent.length, encoding, true);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/decodeQueryComponent.html>
:::
