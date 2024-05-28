[dart:html](../../dart-html/dart-html-library){._links-link}

shuffle method
==============

::: {.section .multi-line-signature}
void shuffle(

1.  \[[Random](../../dart-math/random-class)? random\]

)

::: {.features}
override
:::
:::

Shuffles the elements of this list randomly.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4, 5];
numbers.shuffle();
print(numbers); // [1, 3, 4, 5, 2] OR some other random result.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void shuffle([Random? random]) {
  throw new UnsupportedError("Cannot shuffle immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImmutableListMixin/shuffle.html>
:::
