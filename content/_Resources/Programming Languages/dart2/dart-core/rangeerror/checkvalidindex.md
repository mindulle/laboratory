[dart:core](../../dart-core/dart-core-library){._links-link}

checkValidIndex method
======================

::: {.section .multi-line-signature}
[int](../int-class) checkValidIndex(

1.  [int](../int-class) index,
2.  dynamic indexable,
3.  \[[String](../string-class)? name,
4.  [int](../int-class)? length,
5.  [String](../string-class)? message\]

)
:::

Check that `index` is a valid index into an indexable object.

Throws if `index` is not a valid index into `indexable`.

An indexable object is one that has a `length` and a and index-operator
`[]` that accepts an index if `0 <= index < length`.

If `name` or `message` are provided, they are used as the parameter name
and message text of the thrown error. If `name` is omitted, it defaults
to `"index"`.

If `length` is provided, it is used as the length of the indexable
object, otherwise the length is found as `indexable.length`.

Returns `index` if it is a valid index.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static int checkValidIndex(int index, dynamic indexable,
    [String? name, int? length, String? message]) {
  length ??= (indexable.length as int);
  // Comparing with `0` as receiver produces better dart2js type inference.
  if (0 > index || index >= length) {
    name ??= "index";
    throw RangeError.index(index, indexable, name, message, length);
  }
  return index;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/checkValidIndex.html>
:::
