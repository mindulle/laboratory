[dart:collection](../../dart-collection/dart-collection-library){._links-link}

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
  random ??= Random();
  if (random == null) throw "!"; // TODO(38493): The `??=` should promote.

  int length = this.length;
  while (length > 1) {
    int pos = random.nextInt(length);
    length -= 1;
    var tmp = this[length];
    this[length] = this[pos];
    this[pos] = tmp;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/shuffle.html>
:::
