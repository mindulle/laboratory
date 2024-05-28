[dart:html](../../dart-html/dart-html-library){._links-link}

dataset property
================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
[String](../../dart-core/string-class)\> dataset
:::

Allows access to all custom data attributes (data-\*) set on this
element.

Any data attributes in the markup will be converted to camel-cased keys
in the map based on [these conversion
rules](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dataset).

For example, HTML specified as:

``` {.language-dart data-language="dart"}
<div data-my-random-value='value'></div>
```

Would be accessed in Dart as:

``` {.language-dart data-language="dart"}
var value = element.dataset['myRandomValue'];
```

See also:

-   [HTML data-\* attributes naming
    restrictions](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
-   [Custom data
    attributes](http://dev.w3.org/html5/spec-preview/global-attributes.html#custom-data-attribute)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<String, String> get dataset => new _DataAttributeMap(attributes);
```

::: {#setter .section .multi-line-signature}
void
dataset=([Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
[String](../../dart-core/string-class)\> value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set dataset(Map<String, String> value) {
  final data = this.dataset;
  data.clear();
  for (String key in value.keys) {
    data[key] = value[key]!;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/dataset.html>
:::
