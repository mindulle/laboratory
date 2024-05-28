[dart:core](../../dart-core/dart-core-library){._links-link}

Set\<E\>.unmodifiable constructor
=================================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.12\")

</div>

Set\<E\>.unmodifiable(

1.  [Iterable](../iterable-class)\<E\> elements

)
:::

Creates an unmodifiable [Set](../set-class) from `elements`.

The new set behaves like the result of [Set.of](set.of), except that the
set returned by this constructor is not modifiable.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
final unmodifiableSet = Set.unmodifiable(characters);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.12")
factory Set.unmodifiable(Iterable<E> elements) =>
    UnmodifiableSetView<E>(<E>{...elements});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/Set.unmodifiable.html>
:::
