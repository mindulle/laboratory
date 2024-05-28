[dart:html](../../dart-html/dart-html-library){._links-link}

selectedOptions property
========================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[OptionElement](../optionelement-class)\>
selectedOptions
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<OptionElement> get selectedOptions {
  // IE does not change the selected flag for single-selection items.
  if (this.multiple!) {
    var options = this.options.where((o) => o.selected).toList();
    return new UnmodifiableListView(options);
  } else {
    return [this.options[this.selectedIndex!]];
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SelectElement/selectedOptions.html>
:::
