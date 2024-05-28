[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) remove(

1.  dynamic key

)

::: {.features}
override
:::
:::

Removes `key` and its associated value, if present, from the map.

Returns the value associated with `key` before it was removed. Returns
`null` if `key` was not in the map.

Note that some maps allow `null` as a value, so a returned `null` value
doesn\'t always mean that the key was absent.

``` {.language-dart data-language="dart"}
final terrestrial = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Earth'};
final removedValue = terrestrial.remove(2); // Venus
print(terrestrial); // {1: Mercury, 3: Earth}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String remove(dynamic key) {
  throw new UnsupportedError("Not supported");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioParamMap/remove.html>
:::
