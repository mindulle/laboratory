CSS at-rule functions
=====================

**[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) functions** are at-rule statements that represent
complex rules or can invoke special data processing or calculations.

Syntax
------

[css]

```css
@identifier function([argument]? [, argument]!) {
}
```

The syntax begins with the at symbol `@` and an at-rule identifier, such
as `import`. This is followed by the **name of the at-rule function**,
such as `url`, followed by a pair of opening and closing parentheses.
One or more arguments are specified inside the parentheses.

Some at-rule functions can take multiple arguments, which are formatted
similar to CSS property values. White space is allowed, but it is
optional inside the parentheses. Multiple arguments can be separated
using a comma or a space.

\@import functions
------------------

The [`@import`](@import.md) at-rule is used to import styles from other
stylesheets.

[`@import url()`](@import.md)

:   Imports a stylesheet file from the specified URL.

[`@import src()`](@import.md)

:   Imports a stylesheet file from the specified source.

[`@import supports()`](@import.md)

:   Imports a stylesheet file based on browser support.

[`@import layer()`](@import.md)

:   Imports a stylesheet file into the specified cascade layer.

\@supports functions
--------------------

The [`@supports`](@supports.md) at-rule checks for a browser\'s support for
the specified CSS feature and then applies the CSS styling.

[`@supports selector()`](@supports.md)

:   Applies CSS rules after checking browser\'s support for the
    specified selector syntax.

[`@supports font-tech()`](@supports.md)

:   Applies CSS rules after checking browser\'s support for the
    specified font technology.

[`@supports font-format()`](@supports.md)

:   Applies CSS rules after checking browser\'s support for the
    specified font format.

\@namespace functions
---------------------

The [`@namespace`](@namespace.md) at-rule is used to specify XML namespaces
to be used in a CSS stylesheet.

[`@namespace url()`](@namespace.md)

:   Defines XML namespace from the specified URL.

[`@namespace src()`](@namespace.md)

:   Defines XML namespace from the specified source.

\@container functions
---------------------

The [`@container`](@container.md) at-rule is used to specify styles for a
containment context.

[`@container style()`](@container.md)

:   Defines the containment context style.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule-functions>
