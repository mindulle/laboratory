[dart:core](../../dart-core/dart-core-library){._links-link}

firstMatch method
=================

::: {.section .multi-line-signature}
[RegExpMatch](../regexpmatch-class)? firstMatch(

1.  [String](../string-class) input

)
:::

Finds the first match of the regular expression in the string `input`.

Returns `null` if there is no match.

``` {.language-dart data-language="dart"}
final string = '[00:13.37] This is a chat message.';
final regExp = RegExp(r'c\w*');
final match = regExp.firstMatch(string)!;
print(match[0]); // chat
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RegExpMatch? firstMatch(String input);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/firstMatch.html>
:::
