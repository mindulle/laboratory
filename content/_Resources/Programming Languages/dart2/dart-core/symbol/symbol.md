[dart:core](../../dart-core/dart-core-library){._links-link}

Symbol constructor
==================

::: {.section .multi-line-signature}
const Symbol(

1.  [String](../string-class) name

)
:::

Constructs a new [Symbol](../symbol-class) representing the provided
name.

Symbols created from equal `name` strings are themselves equal. If the
symbols are created using `const`, symbols with the same `name` strings
are canonicalized and identical.

Some `name` strings create symbols which can also be created using a
symbol literal, or be implicitly created while running Dart programs,
for example through [Object.noSuchMethod](../object/nosuchmethod).

If `name` is a single Dart identifier that does not start with an
underscore, or it is a qualified identifier (multiple identifiers
separated by `.`s), or it is the name of a user definable operator
different from `unary-` (one of \"`+`\", \"`-`\", \"`*`\", \"`/`\",
\"`%`\", \"`~/`\", \"`&`\", \"`|`\", \"`^`\", \"`~`\", \"`<<`\",
\"`>>`\", \"`>>>`\", \"`<`\", \"`<=`\", \"`>`\", \"`>=`\", \"`==`\",
\"`[]`\", or \"`[]=`\"), then the result of `Symbol(name)` is equal to
the symbol literal created by prefixing `#` to the contents of `name`,
and `const Symbol(name)` is identical to that symbol literal. That is
`#foo == Symbol("foo")` and `identical(#foo, const Symbol("foo"))`.

If `name` is a single identifier that does not start with an underscore
followed by a `=`, then the symbol is a setter name, and can be equal to
the [Invocation.memberName](../invocation/membername) in an
[Object.noSuchMethod](../object/nosuchmethod) invocation.

Private symbol literals, like `#_foo`, cannot be created using the
symbol constructor. A symbol like `const Symbol("_foo")` is not equal to
any symbol literal, or to any source name symbol introduced by
`noSuchMethod`.

``` {.language-dart data-language="dart"}
assert(Symbol("foo") == Symbol("foo"));
assert(Symbol("foo") == #foo);
assert(identical(const Symbol("foo"), const Symbol("foo")));
assert(identical(const Symbol("foo"), #foo));
assert(Symbol("[]=") == #[]=]);
assert(identical(const Symbol("[]="), #[]=));
assert(Symbol("foo.bar") == #foo.bar);
assert(identical(const Symbol("foo.bar"), #foo.bar));
```

The created instance overrides [Object.==](../object/operator_equals).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const factory Symbol(String name) = internal.Symbol;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Symbol/Symbol.html>
:::
