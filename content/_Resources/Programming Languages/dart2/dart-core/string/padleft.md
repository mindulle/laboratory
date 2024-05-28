[dart:core](../../dart-core/dart-core-library){._links-link}

padLeft method
==============

::: {.section .multi-line-signature}
[String](../string-class) padLeft(

1.  [int](../int-class) width,
2.  \[[String](../string-class) padding = \' \'\]

)
:::

Pads this string on the left if it is shorter than `width`.

Returns a new string that prepends `padding` onto this string one time
for each position the length is less than `width`.

``` {.language-dart data-language="dart"}
const string = 'D';
print(string.padLeft(4)); // '   D'
print(string.padLeft(2, 'x')); // 'xD'
print(string.padLeft(4, 'y')); // 'yyyD'
print(string.padLeft(4, '>>')); // '>>>>>>D'
```

If `width` is already smaller than or equal to `this.length`, no padding
is added. A negative `width` is treated as zero.

If `padding` has length different from 1, the result will not have
length `width`. This may be useful for cases where the padding is a
longer string representing a single character, like `"&nbsp;"` or
`"\u{10002}`\". In that case, the user should make sure that
`this.length` is the correct measure of the string\'s length.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String padLeft(int width, [String padding = ' ']);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/padLeft.html>
:::
