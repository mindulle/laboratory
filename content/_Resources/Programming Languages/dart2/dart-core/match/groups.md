[dart:core](../../dart-core/dart-core-library){._links-link}

groups method
=============

::: {.section .multi-line-signature}
[List](../list-class)\<[String](../string-class)?\> groups(

1.  [List](../list-class)\<[int](../int-class)\> groupIndices

)
:::

A list of the groups with the given indices.

The list contains the strings returned by [group](group) for each index
in `groupIndices`.

``` {.language-dart data-language="dart"}
final string = '[00:13.37] This is a chat message.';
final regExp = RegExp(r'^\[\s*(\d+):(\d+)\.(\d+)\]\s*(.*)$');
final match = regExp.firstMatch(string)!;
final message = jsonEncode(match.groups([1, 2, 3, 4]));
// ['00','13','37','This is a chat message.']
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<String?> groups(List<int> groupIndices);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Match/groups.html>
:::
