[dart:core](../../dart-core/dart-core-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[double](../double-class) parse(

1.  [String](../string-class) source,
2.  \[@[deprecated](../deprecated-constant) [double](../double-class)
    onError(
    1.  [String](../string-class) source

    )?\]

)

::: {.features}
override
:::
:::

Parse `source` as a double literal and return its value.

Accepts an optional sign (`+` or `-`) followed by either the characters
\"Infinity\", the characters \"NaN\" or a floating-point representation.
A floating-point representation is composed of a mantissa and an
optional exponent part. The mantissa is either a decimal point (`.`)
followed by a sequence of (decimal) digits, or a sequence of digits
optionally followed by a decimal point and optionally more digits. The
(optional) exponent part consists of the character \"e\" or \"E\", an
optional sign, and one or more digits. The `source` must not be `null`.

Leading and trailing whitespace is ignored.

If the `source` string is not a valid double literal, the `onError` is
called with the `source` as argument, and its return value is used
instead. Throws a [FormatException](../formatexception-class) if the
`source` string is not valid and no `onError` is provided.

Examples of accepted strings:

``` {.language-dart data-language="dart"}
"3.14"
"  3.14 \xA0"
"0."
".0"
"-1.e3"
"1234E+7"
"+.12e-9"
"-NaN"
```

The `onError` parameter is deprecated and will be removed. Instead of
`double.parse(string, (string) { ... })`, you should use
`double.tryParse(string) ?? (...)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static double parse(String source,
    [@deprecated double onError(String source)?]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/parse.html>
:::
