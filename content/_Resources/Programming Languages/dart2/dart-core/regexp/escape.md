[dart:core](../../dart-core/dart-core-library){._links-link}

escape method
=============

::: {.section .multi-line-signature}
[String](../string-class) escape(

1.  [String](../string-class) text

)
:::

Creates regular expression syntax that matches `text`.

If `text` contains characters that are meaningful in regular
expressions, the resulting regular expression will match those
characters literally. If `text` contains no characters that have special
meaning in a regular expression, it is returned unmodified.

The characters that have special meaning in regular expressions are:
`(`, `)`, `[`, `]`, `{`, `}`, `*`, `+`, `?`, `.`, `^`, `$`, `|` and `\`.

This method is mainly used to create a pattern to be included in a
larger regular expression. Since a [String](../string-class) is itself a
[Pattern](../pattern-class) which matches itself, converting the string
to a regular expression isn\'t needed in order to search for just that
string.

``` {.language-dart data-language="dart"}
print(RegExp.escape('dash@example.com')); // dash@example\.com
print(RegExp.escape('a+b')); // a\+b
print(RegExp.escape('a*b')); // a\*b
print(RegExp.escape('{a-b}')); // \{a-b\}
print(RegExp.escape('a?')); // a\?
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static String escape(String text);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/escape.html>
:::
