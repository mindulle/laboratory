[dart:core](../../dart-core/dart-core-library){._links-link}

copyRange\<T\> method
=====================

::: {.section .multi-line-signature}
void copyRange\<T\>(

1.  [List](../list-class)\<T\> target,
2.  [int](../int-class) at,
3.  [List](../list-class)\<T\> source,
4.  \[[int](../int-class)? start,
5.  [int](../int-class)? end\]

)
:::

Copy a range of one list into another list.

This is a utility function that can be used to implement methods like
[setRange](setrange).

The range from `start` to `end` must be a valid range of `source`, and
there must be room for `end - start` elements from position `at`. If
`start` is omitted, it defaults to zero. If `end` is omitted, it
defaults to `source`.length.

If `source` and `target` are the same list, overlapping source and
target ranges are respected so that the target range ends up containing
the initial content of the source range. Otherwise the order of element
copying is not guaranteed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void copyRange<T>(List<T> target, int at, List<T> source,
    [int? start, int? end]) {
  start ??= 0;
  end = RangeError.checkValidRange(start, end, source.length);
  if (end == null) {
    // TODO(dart-lang/language#440): Remove when promotion works.
    throw "unreachable";
  }
  int length = end - start;
  if (target.length < at + length) {
    throw ArgumentError.value(target, "target",
        "Not big enough to hold $length elements at position $at");
  }
  if (!identical(source, target) || start >= at) {
    for (int i = 0; i < length; i++) {
      target[at + i] = source[start + i];
    }
  } else {
    for (int i = length; --i >= 0;) {
      target[at + i] = source[start + i];
    }
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/copyRange.html>
:::
