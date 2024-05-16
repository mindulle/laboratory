all
===

The `all` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property resets
all of an element\'s properties except [`unicode-bidi`](unicode-bidi.md),
[`direction`](direction.md), and [](using_css_custom_properties.md). It can set properties to their
initial or inherited values, or to the values specified in another
cascade layer or stylesheet origin.

Try it
------

Constituent properties
----------------------

This property is a shorthand for all CSS properties except for
[`unicode-bidi`](unicode-bidi.md), [`direction`](direction.md), and [](using_css_custom_properties.md).

Syntax
------

[css]

```css
/* Global values */
all: initial;
all: inherit;
all: unset;
all: revert;
all: revert-layer;
```

The `all` property is specified as one of the CSS global keyword values.
Note that none of these values affect the [`unicode-bidi`](unicode-bidi.md)
and [`direction`](direction.md) properties.

### Values

[`initial`](initial.md)

:   Specifies that all the element\'s properties should be changed to
    their [initial values](initial_value.md).

[`inherit`](inherit.md)

:   Specifies that all the element\'s properties should be changed to
    their [inherited values](inheritance.md).

[`unset`](unset.md)

:   Specifies that all the element\'s properties should be changed to
    their inherited values if they inherit by default, or to their
    initial values if not.

[`revert`](revert.md)

:   Specifies behavior that depends on the stylesheet origin to which
    the declaration belongs:

    -   If the rule belongs to the [author
        origin](cascade#author_stylesheets), the `revert` value rolls
        back the [cascade](cascade) to the user level, so that the
        [specified values](specified_value) are calculated as if no
        author-level rules were specified for the element. For purposes
        of `revert`, the author origin includes the Override and
        Animation origins.
    -   If the rule belongs to the [user
        origin](cascade#user_stylesheets), the `revert` value rolls back
        the [cascade](cascade) to the user-agent level, so that the
        [specified values](specified_value) are calculated as if no
        author-level or user-level rules were specified for the element.
    -   If the rule belongs to the [user-agent
        origin](cascade#user-agent_stylesheets), the `revert` value acts
        like `unset`.

[`revert-layer`](revert-layer.md)

:   Specifies that all the element\'s properties should roll back the
    cascade to a previous [cascade layer](@layer.md), if one exists. If no
    other cascade layer exists, the element\'s properties will roll back
    to the matching rule, if one exists, in the current layer or to a
    previous [style
    origin](https://developer.mozilla.org/en-US/docs/Glossary/Style_origin).

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     There is no practical initial value for it.
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as the specified value applies to each property this is a shorthand for.
  Animation type                     as each of the properties of the shorthand (all properties but [`unicode-bidi`](unicode-bidi.md) and [`direction`](direction.md))
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
all = 
  initial       |
  inherit       |
  unset         |
  revert        |
  revert-layer  
```

Examples
--------

In this example, the CSS file contains styling for the
[`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
element in addition to some styling for the parent `<body>` element.
Various outputs in the Results subsection demonstrate how the styling of
the `<blockquote>` element is affected when different values are applied
to the `all` property inside the `blockquote` rule.

### HTML

[html]

```html
<blockquote id="quote">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
</blockquote>
Phasellus eget velit sagittis.
```

### CSS

[css]

```css
body {
  font-size: small;
  background-color: #f0f0f0;
  color: blue;
  margin: 0;
  padding: 0;
}

blockquote {
  background-color: skyblue;
  color: red;
}
```

### Results

#### A. No `all` property

This is the scenario in which no `all` property is set inside the
`blockquote` rule. The
[`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
element uses the browser\'s default styling which gives it a margin,
together with a specific background and text color as specified in the
stylesheet. It also behaves as a *block* element: the text that follows
it is beneath it.

#### B. `all: initial`

With the `all` property set to `initial` in the `blockquote` rule, the
[`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
element doesn\'t use the browser default styling anymore: it is an
*inline* element now (initial value), its
[`background-color`](background-color.md#formal_definition) is
`transparent` (initial value), its
[`font-size`](font-size.md#formal_definition) is `medium`, and its
[`color`](_Resources/Markup%20And%20Styling/css/color.md#formal_definition) is `black` (initial value).

#### C. `all: inherit`

In this case, the
[`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
element doesn\'t use the browser default styling. Instead, it inherits
style values from its parent
[`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)
element: it is a *block* element now (inherited value), its
[`background-color`](background-color.md) is `#F0F0F0` (inherited value),
its [`font-size`](font-size.md) is `small` (inherited value), and its
[`color`](_Resources/Markup%20And%20Styling/css/color.md) is `blue` (inherited value).

#### D. `all: unset`

When the `unset` value is applied to the `all` property in the
`blockquote` rule, the
[`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
element doesn\'t use the browser default styling. Because
[`background-color`](background-color.md#formal_definition) is a
non-inherited property and [`font-size`](font-size.md#formal_definition)
and [`color`](_Resources/Markup%20And%20Styling/css/color.md#formal_definition) are inherited properties, the
`<blockquote>` element is an *inline* element now (initial value), its
[`background-color`](background-color.md) is `transparent` (initial value),
but its [`font-size`](font-size.md) is still `small` (inherited value), and
its [`color`](_Resources/Markup%20And%20Styling/css/color.md) is `blue` (inherited value).

#### E. `all: revert`

When the `all` property is set to `revert` in the `blockquote` rule, the
`blockquote` rule is considered to be non-existent and the styling
property values are inherited from the ones applied to the parent
element `<body>`. So the `<blockquote>` element gets styled as a *block*
element, with [`background-color`](background-color.md) `#F0F0F0`,
[`font-size`](font-size.md) `small`, and [`color`](_Resources/Markup%20And%20Styling/css/color.md) `blue` - all
values inherited from the `body` rule.

#### F. `all: revert-layer`

There are no cascade layers defined in the CSS file, so the
`<blockquote>` element inherits its style from the matching `body` rule.
The `<blockquote>` element here is styled as a *block* element, with
[`background-color`](background-color.md) `#F0F0F0`,
[`font-size`](font-size.md) `small`, and [`color`](_Resources/Markup%20And%20Styling/css/color.md) `blue` - all
values inherited from the `body` rule. This scenario is an example of
the case when `all` set to `revert-layer` behaves the same as when `all`
is set to `revert`.

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Cascading and Inheritance Level 4\
  [\#
  all-shorthand]](https://drafts.csswg.org/css-cascade/#all-shorthand)

  ------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`all`

37

79

27

No

24

9.1

37

37

27

24

9.3

3.0

See also
--------

CSS global keyword values: [`initial`](initial.md), [`inherit`](inherit.md),
[`unset`](unset.md), [`revert`](revert.md), [`revert-layer`](revert-layer.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/all>
