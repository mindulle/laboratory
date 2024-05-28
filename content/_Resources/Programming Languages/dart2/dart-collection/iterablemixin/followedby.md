[dart:collection](../../dart-collection/dart-collection-library){._links-link}

followedBy method
=================

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> followedBy(

1.  [Iterable](../../dart-core/iterable-class)\<E\> other

)

::: {.features}
override
:::
:::

Returns the lazy concatenation of this iterable and `other`.

The returned iterable will provide the same elements as this iterable,
and, after that, the elements of `other`, in the same order as in the
original iterables.

Example:

``` {.language-dart data-language="dart"}
var planets = <String>['Earth', 'Jupiter'];
var updated = planets.followedBy(['Mars', 'Venus']);
print(updated); // (Earth, Jupiter, Mars, Venus)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> followedBy(Iterable<E> other) {
  // Type workaround because IterableMixin<E> doesn't promote
  // to EfficientLengthIterable<E>.
  Iterable<E> self = this;
  if (self is EfficientLengthIterable<E>) {
    return FollowedByIterable<E>.firstEfficient(self, other);
  }
  return FollowedByIterable<E>(this, other);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableMixin/followedBy.html>
:::
