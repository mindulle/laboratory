[dart:core](../../dart-core/dart-core-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[int](../int-class) parse(

1.  [String](../string-class) source,
2.  {[int](../int-class)? radix,
3.  @[deprecated](../deprecated-constant) [int](../int-class) onError(
    1.  [String](../string-class) source

    )?}

)

::: {.features}
override
:::
:::

Parse `source` as a, possibly signed, integer literal and return its
value.

The `source` must be a non-empty sequence of base-`radix` digits,
optionally prefixed with a minus or plus sign (\'-\' or \'+\').

The `radix` must be in the range 2..36. The digits used are first the
decimal digits 0..9, and then the letters \'a\'..\'z\' with values 10
through 35. Also accepts upper-case letters with the same values as the
lower-case ones.

If no `radix` is given then it defaults to 10. In this case, the
`source` digits may also start with `0x`, in which case the number is
interpreted as a hexadecimal integer literal, When `int` is implemented
by 64-bit signed integers, hexadecimal integer literals may represent
values larger than 2^63^, in which case the value is parsed as if it is
an *unsigned* number, and the resulting value is the corresponding
signed integer value.

For any int `n` and valid radix `r`, it is guaranteed that
`n == int.parse(n.toRadixString(r), radix: r)`.

If the `source` string does not contain a valid integer literal,
optionally prefixed by a sign, a
[FormatException](../formatexception-class) is thrown (unless the
deprecated `onError` parameter is used, see below).

Instead of throwing and immediately catching the
[FormatException](../formatexception-class), instead use
[tryParse](tryparse) to handle a parsing error.

Example:

``` {.language-dart data-language="dart"}
var value = int.tryParse(text);
if (value == null) {
  // handle the problem
  // ...
}
```

The `onError` parameter is deprecated and will be removed. Instead of
`int.parse(string, onError: (string) => ...)`, you should use
`int.tryParse(string) ?? (...)`.

When the source string is not valid and `onError` is provided, whenever
a [FormatException](../formatexception-class) would be thrown, `onError`
is instead called with `source` as argument, and the result of that call
is returned by [parse](parse).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static int parse(String source,
    {int? radix, @deprecated int onError(String source)?});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/parse.html>
:::
