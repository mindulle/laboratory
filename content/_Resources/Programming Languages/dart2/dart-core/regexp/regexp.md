[dart:core](../../dart-core/dart-core-library){._links-link}

RegExp constructor
==================

::: {.section .multi-line-signature}
RegExp(

1.  [String](../string-class) source,
2.  {[bool](../bool-class) multiLine = false,
3.  [bool](../bool-class) caseSensitive = true,
4.  \@Since(\"2.4\") [bool](../bool-class) unicode = false,
5.  \@Since(\"2.4\") [bool](../bool-class) dotAll = false}

)
:::

Constructs a regular expression.

Throws a [FormatException](../formatexception-class) if `source` is not
valid regular expression syntax.

If `multiLine` is enabled, then `^` and `$` will match the beginning and
end of a *line*, in addition to matching beginning and end of input,
respectively.

If `caseSensitive` is disabled, then case is ignored.

If `unicode` is enabled, then the pattern is treated as a Unicode
pattern as described by the ECMAScript standard.

If `dotAll` is enabled, then the `.` pattern will match *all*
characters, including line terminators.

Example:

``` {.language-dart data-language="dart"}
final wordPattern = RegExp(r'(\w+)');
final digitPattern = RegExp(r'(\d+)');
```

Notice the use of a *raw string* in the first example, and a regular
string in the second. Because of the many escapes, like `\d`, used in
regular expressions, it is common to use a raw string here, unless
string interpolation is required.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory RegExp(String source,
    {bool multiLine = false,
    bool caseSensitive = true,
    @Since("2.4") bool unicode = false,
    @Since("2.4") bool dotAll = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/RegExp.html>
:::
