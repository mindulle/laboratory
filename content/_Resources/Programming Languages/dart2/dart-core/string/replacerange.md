[dart:core](../../dart-core/dart-core-library){._links-link}

replaceRange method
===================

::: {.section .multi-line-signature}
[String](../string-class) replaceRange(

1.  [int](../int-class) start,
2.  [int](../int-class)? end,
3.  [String](../string-class) replacement

)
:::

Replaces the substring from `start` to `end` with `replacement`.

Creates a new string equivalent to:

``` {.language-dart data-language="dart"}
this.substring(0, start) + replacement + this.substring(end)
```

Example:

``` {.language-dart data-language="dart"}
const string = 'Dart is fun';
final result = string.replaceRange(8, null, 'open source');
print(result); // Dart is open source
```

The `start` and `end` indices must specify a valid range of this string.
That is `0 <= start <= end <= this.length`. If `end` is `null`, it
defaults to [length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String replaceRange(int start, int? end, String replacement);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/replaceRange.html>
:::
