[dart:core](../../dart-core/dart-core-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[num](../num-class) parse(

1.  [String](../string-class) input,
2.  \[@[deprecated](../deprecated-constant) [num](../num-class) onError(
    1.  [String](../string-class) input

    )?\]

)
:::

Parses a string containing a number literal into a number.

The method first tries to read the `input` as integer (similar to
[int.parse](../int/parse) without a radix). If that fails, it tries to
parse the `input` as a double (similar to
[double.parse](../double/parse)). If that fails, too, it invokes
`onError` with `input`, and the result of that invocation becomes the
result of calling `parse`.

If no `onError` is supplied, it defaults to a function that throws a
[FormatException](../formatexception-class).

For any number `n`, this function satisfies
`identical(n, num.parse(n.toString()))` (except when `n` is a NaN
`double` with a payload).

The `onError` parameter is deprecated and will be removed. Instead of
`num.parse(string, (string) { ... })`, you should use
`num.tryParse(string) ?? (...)`.

Examples:

``` {.language-dart data-language="dart"}
var value = num.parse('2021'); // 2021
value = num.parse('3.14'); // 3.14
value = num.parse('  3.14 \xA0'); // 3.14
value = num.parse('0.'); // 0.0
value = num.parse('.0'); // 0.0
value = num.parse('-1.e3'); // -1000.0
value = num.parse('1234E+7'); // 12340000000.0
value = num.parse('+.12e-9'); // 1.2e-10
value = num.parse('-NaN'); // NaN
value = num.parse('0xFF'); // 255
value = num.parse(double.infinity.toString()); // Infinity
value = num.parse('1f'); // Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static num parse(String input, [@deprecated num onError(String input)?]) {
  num? result = tryParse(input);
  if (result != null) return result;
  if (onError == null) throw FormatException(input);
  return onError(input);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/parse.html>
:::
