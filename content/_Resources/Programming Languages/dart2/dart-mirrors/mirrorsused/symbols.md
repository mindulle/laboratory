[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

symbols property
================

::: {.section .multi-line-signature}
dynamic symbols

::: {.features}
final
:::
:::

The list of strings passed to new
[Symbol](../../dart-core/symbol-class), and symbols that might be passed
to [MirrorSystem.getName](../mirrorsystem/getname).

Combined with the names of [targets](targets),
[metaTargets](metatargets) and their members, this forms the complete
list of strings passed to new [Symbol](../../dart-core/symbol-class),
and symbols that might be passed to
[MirrorSystem.getName](../mirrorsystem/getname) by the library to which
this metadata applies.

The following text is non-normative:

Dart2js currently supports the following formats to specify symbols:

-   A constant [List](../../dart-core/list-class) of
    [String](../../dart-core/string-class) constants representing symbol
    names, e.g., `const ['foo', 'bar']`.
-   A single [String](../../dart-core/string-class) constant whose value
    is a comma-separated list of symbol names, e.g., `"foo, bar"`.

Specifying the `symbols` field turns off the following warnings emitted
by dart2js:

-   Using \"MirrorSystem.getName\" may result in larger output.
-   Using \"new Symbol\" may result in larger output.

For example, if you\'re using
[noSuchMethod](../../dart-core/object/nosuchmethod) to interact with a
database, extract all the possible column names and include them in this
list. Similarly, if you\'re using
[noSuchMethod](../../dart-core/object/nosuchmethod) to interact with
another language (JavaScript, for example) extract all the identifiers
from the API you use and include them in this list.

Note that specifying a symbol only ensures that the symbol will be
available under that name at runtime. It does not mark targets with that
name as available for reflection. See [targets](targets) and
[metaTargets](metatargets) for that purpose.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final symbols;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorsUsed/symbols.html>
:::
