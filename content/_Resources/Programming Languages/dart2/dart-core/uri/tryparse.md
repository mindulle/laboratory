[dart:core](../../dart-core/dart-core-library){._links-link}

tryParse method
===============

::: {.section .multi-line-signature}
[Uri](../uri-class)? tryParse(

1.  [String](../string-class) uri,
2.  \[[int](../int-class) start = 0,
3.  [int](../int-class)? end\]

)
:::

Creates a new `Uri` object by parsing a URI string.

If `start` and `end` are provided, they must specify a valid substring
of `uri`, and only the substring from `start` to `end` is parsed as a
URI.

Returns `null` if the `uri` string is not valid as a URI or URI
reference.

Example:

``` {.language-dart data-language="dart"}
final uri = Uri.tryParse(
    'https://dart.dev/guides/libraries/library-tour#utility-classes', 0,
    16);
print(uri); // https://dart.dev

var notUri = Uri.tryParse('::Not valid URI::');
print(notUri); // null
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Uri? tryParse(String uri, [int start = 0, int? end]) {
  // TODO: Optimize to avoid throwing-and-recatching.
  try {
    return parse(uri, start, end);
  } on FormatException {
    return null;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/tryParse.html>
:::
