CSS nesting
===========

The **CSS nesting** module defines a syntax for nesting selectors,
providing the ability to nest one style rule inside another, with the
selector of the child rule relative to the selector of the parent rule.

CSS nesting is different from CSS preprocessors such as
[Sass](https://sass-lang.com/) in that it is parsed by the browser
rather than being pre-compiled by a CSS preprocessor.

CSS nesting helps with the readability, modularity, and maintainability
of CSS stylesheets. It also potentially helps reduce the size of CSS
files, thereby decreasing the amount of data downloaded by users.

Reference
---------

### Selectors

- [`&` nesting selector](nesting_selector.md)

Guides
------

[Using CSS nesting](using_css_nesting.md)

:   Explains how to use CSS nesting.

[CSS nesting at-rules](nesting_at-rules.md)

:   Explains how to nest at-rules.

[CSS nesting and specificity](nesting_and_specificity.md)

:   Explains the differences in specificity when nesting CSS.

Related concepts
----------------

- [Selectors and combinators](selectors_and_combinators.md)
- [Pseudo-classes](pseudo-classes.md)
- [CSS
    preprocessor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor)

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Nesting Module\
  ](https://drafts.csswg.org/css-nesting-1/)

  -----------------------------------------------------------------------

See also
--------

- [Specificity](specificity.md)
- [CSS cascade and inheritance module](css_cascade.md)
- [CSS selectors module](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting>
