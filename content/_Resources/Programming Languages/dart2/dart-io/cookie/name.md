[dart:io](../../dart-io/dart-io-library){._links-link}

name property
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) name

::: {.features}
read / write
:::
:::

The name of the cookie.

Must be a `token` as specified in RFC 6265.

The allowed characters in a `token` are the visible ASCII characters,
U+0021 (`!`) through U+007E (`~`), except the separator characters: `(`,
`)`, `<`, `>`, `@`, `,`, `;`, `:`, `\`, `"`, `/`, `[`, `]`, `?`, `=`,
`{`, and `}`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
late String name;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Cookie/name.html>
:::
