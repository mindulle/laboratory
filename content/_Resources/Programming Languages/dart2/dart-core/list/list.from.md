[dart:core](../../dart-core/dart-core-library){._links-link}

List\<E\>.from constructor
==========================

::: {.section .multi-line-signature}
List\<E\>.from(

1.  [Iterable](../iterable-class) elements,
2.  {[bool](../bool-class) growable = true}

)
:::

Creates a list containing all `elements`.

The [Iterator](../iterator-class) of `elements` provides the order of
the elements.

All the `elements` should be instances of `E`.

Example:

``` {.language-dart data-language="dart"}
final numbers = <num>[1, 2, 3];
final listFrom = List<int>.from(numbers);
print(listFrom); // [1, 2, 3]
```

The `elements` iterable itself may have any element type, so this
constructor can be used to down-cast a `List`, for example as:

``` {.language-dart data-language="dart"}
const jsonArray = '''
  [{"text": "foo", "value": 1, "status": true},
   {"text": "bar", "value": 2, "status": false}]
''';
final List<dynamic> dynamicList = jsonDecode(jsonArray);
final List<Map<String, dynamic>> fooData =
    List.from(dynamicList.where((x) => x is Map && x['text'] == 'foo'));
print(fooData); // [{text: foo, value: 1, status: true}]
```

This constructor creates a growable list when `growable` is true;
otherwise, it returns a fixed-length list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory List.from(Iterable elements, {bool growable = true});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/List.from.html>
:::
