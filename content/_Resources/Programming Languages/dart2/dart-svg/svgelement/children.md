[dart:svg](../../dart-svg/dart-svg-library){._links-link}

children property
=================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[Element](../../dart-html/element-class)\>
children

::: {.features}
override
:::
:::

List of the direct children of this element.

This collection can be used to add and remove elements from the
document.

``` {.language-dart data-language="dart"}
var item = new DivElement();
item.text = 'Something';
document.body.children.add(item) // Item is now displayed on the page.
for (var element in document.body.children) {
  element.style.background = 'red'; // Turns every child of body red.
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Element> get children => new FilteredElementList(this);
```

::: {#setter .section .multi-line-signature}
void
children=([List](../../dart-core/list-class)\<[Element](../../dart-html/element-class)\>
value)

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set children(List<Element> value) {
  final children = this.children;
  children.clear();
  children.addAll(value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/children.html>
:::
