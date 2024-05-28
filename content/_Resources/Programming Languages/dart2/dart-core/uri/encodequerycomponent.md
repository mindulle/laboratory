[dart:core](../../dart-core/dart-core-library){._links-link}

encodeQueryComponent method
===========================

::: {.section .multi-line-signature}
[String](../string-class) encodeQueryComponent(

1.  [String](../string-class) component,
2.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Encodes the string `component` according to the HTML 4.01 rules for
encoding the posting of a HTML form as a query string component.

Encode the string `component` according to the HTML 4.01 rules for
encoding the posting of a HTML form as a query string component.

The component is first encoded to bytes using `encoding`. The default is
to use [utf8](../../dart-convert/utf8-constant) encoding, which
preserves all the characters that don\'t need encoding.

Then the resulting bytes are \"percent-encoded\". This transforms spaces
(U+0020) to a plus sign (\'+\') and all bytes that are not the ASCII
decimal digits, letters or one of \'-.\_\~\' are written as a percent
sign \'%\' followed by the two-digit hexadecimal representation of the
byte.

Note that the set of characters which are percent-encoded is a superset
of what HTML 4.01 requires, since it refers to RFC 1738 for reserved
characters.

When manually encoding query components remember to encode each part
separately before building the query string.

To avoid the need for explicitly encoding the query use the
[queryParameters](queryparameters) optional named arguments when
constructing a [Uri](../uri-class).

See <https://www.w3.org/TR/html401/interact/forms.html#h-17.13.4.2> for
more details.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String encodeQueryComponent(String component,
    {Encoding encoding = utf8}) {
  return _Uri._uriEncode(_Uri._unreservedTable, component, encoding, true);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/encodeQueryComponent.html>
:::
