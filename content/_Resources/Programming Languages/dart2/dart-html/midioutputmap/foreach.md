[dart:html](../../dart-html/dart-html-library){._links-link}

forEach method
==============

::: {.section .multi-line-signature}
void forEach(

1.  void f(
    1.  [String](../../dart-core/string-class) key,
    2.  dynamic value

    )

)

::: {.features}
override
:::
:::

Applies `action` to each key/value pair of the map.

Calling `action` must not add or remove keys from the map.

``` {.language-dart data-language="dart"}
final planetsByMass = <num, String>{0.81: 'Venus', 1: 'Earth',
  0.11: 'Mars', 17.15: 'Neptune'};

planetsByMass.forEach((key, value) {
  print('$key: $value');
  // 0.81: Venus
  // 1: Earth
  // 0.11: Mars
  // 17.15: Neptune
});
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void forEach(void f(String key, dynamic value)) {
  var entries = JS('', '#.entries()', this);
  while (true) {
    var entry = JS('', '#.next()', entries);
    if (JS('bool', '#.done', entry)) return;
    f(JS('String', '#.value[0]', entry),
        convertNativeToDart_Dictionary(JS('', '#.value[1]', entry)));
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MidiOutputMap/forEach.html>
:::
