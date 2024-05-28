[dart:io](../../dart-io/dart-io-library){._links-link}

value property
==============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) value

::: {.features}
read / write
:::
:::

The value of the cookie.

Must be a `cookie-value` as specified in RFC 6265.

The allowed characters in a cookie value are the visible ASCII
characters, U+0021 (`!`) through U+007E (`~`) except the characters:
`"`, `,`, `;` and `\`. Cookie values may be wrapped in a single pair of
double quotes (U+0022, `"`).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
late String value;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Cookie/value.html>
:::
