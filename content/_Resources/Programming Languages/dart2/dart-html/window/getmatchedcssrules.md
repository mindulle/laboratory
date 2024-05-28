[dart:html](../../dart-html/dart-html-library){._links-link}

getMatchedCssRules method
=========================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'getMatchedCSSRules\')
2.  \@Returns(\'\_CssRuleList\')
3.  \@Creates(\'\_CssRuleList\')

</div>

[List](../../dart-core/list-class)\<[CssRule](../cssrule-class)\>
getMatchedCssRules(

1.  [Element](../element-class)? element,
2.  [String](../../dart-core/string-class)? pseudoElement

)

::: {.features}
\@JSName(\'getMatchedCSSRules\'), \@Returns(\'\_CssRuleList\'),
\@Creates(\'\_CssRuleList\')
:::
:::

Returns all CSS rules that apply to the element\'s pseudo-element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('getMatchedCSSRules')
/**
 * Returns all CSS rules that apply to the element's pseudo-element.
 */
@Returns('_CssRuleList')
@Creates('_CssRuleList')
List<CssRule> getMatchedCssRules(Element? element, String? pseudoElement)
    native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/getMatchedCssRules.html>
:::
