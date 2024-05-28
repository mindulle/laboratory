[dart:core](../../dart-core/dart-core-library){._links-link}

isScheme method
===============

::: {.section .multi-line-signature}
[bool](../bool-class) isScheme(

1.  [String](../string-class) scheme

)
:::

Whether the scheme of this [Uri](../uri-class) is `scheme`.

The `scheme` should be the same as the one returned by
[Uri.scheme](scheme), but doesn\'t have to be case-normalized to
lower-case characters.

Example:

``` {.language-dart data-language="dart"}
var uri = Uri.parse('http://example.com');
print(uri.isScheme('HTTP')); // true

final uriNoScheme = Uri(host: 'example.com');
print(uriNoScheme.isScheme('HTTP')); // false
```

An empty `scheme` string matches a URI with no scheme (one where
[hasScheme](hasscheme) returns false).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool isScheme(String scheme);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/isScheme.html>
:::
