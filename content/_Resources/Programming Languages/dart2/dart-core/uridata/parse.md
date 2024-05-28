[dart:core](../../dart-core/dart-core-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[UriData](../uridata-class) parse(

1.  [String](../string-class) uri

)
:::

Parses a string as a `data` URI.

The string must have the format:

``` {.language-plaintext data-language="dart"}
'data:' (type '/' subtype)? (';' attribute '=' value)* (';base64')? ',' data
```

where `type`, `subtype`, `attribute` and `value` are specified in
RFC-2045, and `data` is a sequence of URI-characters (RFC-2396 `uric`).

This means that all the characters must be ASCII, but the URI may
contain percent-escapes for non-ASCII byte values that need an
interpretation to be converted to the corresponding string.

Parsing checks that Base64 encoded data is valid, and it normalizes it
to use the default Base64 alphabet and to use padding. Non-Base64 data
is escaped using percent-escapes as necessary to make it valid, and
existing escapes are case normalized.

Accessing the individual parts may fail later if they turn out to have
content that cannot be decoded successfully as a string, for example if
existing percent escapes represent bytes that cannot be decoded by the
chosen [Encoding](../../dart-convert/encoding-class) (see
[contentAsString](contentasstring)).

A [FormatException](../formatexception-class) is thrown if `uri` is not
a valid data URI.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static UriData parse(String uri) {
  if (uri.length >= 5) {
    int dataDelta = _startsWithData(uri, 0);
    if (dataDelta == 0) {
      // Exact match on "data:".
      return _parse(uri, 5, null);
    }
    if (dataDelta == 0x20) {
      // Starts with a non-normalized "data" scheme containing upper-case
      // letters. Parse anyway, but throw away the scheme.
      return _parse(uri.substring(5), 0, null);
    }
  }
  throw FormatException("Does not start with 'data:'", uri, 0);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/parse.html>
:::
