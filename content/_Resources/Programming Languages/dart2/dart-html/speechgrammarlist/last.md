[dart:html](../../dart-html/dart-html-library){._links-link}

last property
=============

::: {#getter .section .multi-line-signature}
[SpeechGrammar](../speechgrammar-class) last

::: {.features}
override
:::
:::

Returns the last element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty. Otherwise may iterate through the elements and returns the last
one seen. Some iterables may have more efficient ways to find the last
element (for example a list can directly access the last element,
without iterating through the previous ones).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
SpeechGrammar get last {
  int len = this.length;
  if (len > 0) {
    return JS('SpeechGrammar', '#[#]', this, len - 1);
  }
  throw new StateError("No elements");
}
```

::: {#setter .section .multi-line-signature}
void last=([SpeechGrammar](../speechgrammar-class) value)

::: {.features}
inherited
:::
:::

The last element of the list.

The list must be non-empty when accessing its last element.

The last element of a list can be modified, unlike an
[Iterable](../../dart-core/iterable-class). A `list.last` is equivalent
to `theList[theList.length - 1]`, both for getting and setting the
value.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
print(numbers.last); // 3
numbers.last = 10;
print(numbers.last); // 10
numbers.clear();
numbers.last; // Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set last(E value) {
  if (length == 0) throw IterableElementError.noElement();
  this[length - 1] = value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechGrammarList/last.html>
:::
