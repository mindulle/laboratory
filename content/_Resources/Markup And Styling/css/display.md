display
=======

The `display` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether an element is treated as a [](css_flow_layout.md) and the layout used for its children, such as
[flow layout](css_flow_layout.md), [grid](css_grid_layout.md) or
[flex](css_flexible_box_layout.md).

Formally, the `display` property sets an element\'s inner and outer
*display types*. The outer type sets an element\'s participation in
[flow layout](css_flow_layout.md); the inner type sets the layout of
children. Some values of `display` are fully defined in their own
individual specifications; for example the detail of what happens when
`display: flex` is declared is defined in the CSS Flexible Box Model
specification.

Try it
------

Syntax
------

[css]

```css
/* precomposed values */
display: block;
display: inline;
display: inline-block;
display: flex;
display: inline-flex;
display: grid;
display: inline-grid;
display: flow-root;

/* box generation */
display: none;
display: contents;

/* multi-keyword syntax */
display: block flow;
display: inline flow;
display: inline flow-root;
display: block flex;
display: inline flex;
display: block grid;
display: inline grid;
display: block flow-root;

/* other values */
display: table;
display: table-row; /* all table elements have an equivalent CSS display value */
display: list-item;

/* Global values */
display: inherit;
display: initial;
display: revert;
display: revert-layer;
display: unset;
```

The CSS `display` property is specified using keyword values.

Grouped values
--------------

The keyword values can be grouped into six value categories.

### Outside

[`<display-outside>`](display-outside.md)

:   These keywords specify the element\'s outer display type, which is
    essentially its role in flow layout:

    [`block`](#block)

    :   The element generates a block box, generating line breaks both
        before and after the element when in the normal flow.

    [`inline`](#inline)

    :   The element generates one or more inline boxes that do not
        generate line breaks before or after themselves. In normal flow,
        the next element will be on the same line if there is space.

**Note:** Browsers that support the multi-keyword syntax, on finding the
outer value only, such as when `display: block` or `display: inline` is
specified, will set the inner value to `flow`. This will result in
expected behavior; for example, if you specify an element to be block,
you would expect that the children of that element would participate in
block and inline normal flow layout.

### Inside

[`<display-inside>`](display-inside.md)

:   These keywords specify the element\'s inner display type, which
    defines the type of formatting context that its contents are laid
    out in (assuming it is a non-replaced element):

    [`flow`](#flow) [Experimental]

    :   The element lays out its contents using flow layout
        (block-and-inline layout).

        If its outer display type is `inline` or `run-in`, and it is
        participating in a block or inline formatting context, then it
        generates an inline box. Otherwise it generates a block
        container box.

        Depending on the value of other properties (such as
        [`position`](position), [`float`](float), or
        [`overflow`](overflow)) and whether it is itself participating
        in a block or inline formatting context, it either establishes a
        new [block formatting
        context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
        (BFC) for its contents or integrates its contents into its
        parent formatting context.

    [`flow-root`](#flow-root)

    :   The element generates a block box that establishes a new [block
        formatting
        context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context),
        defining where the formatting root lies.

    [`table`](#table)

    :   These elements behave like HTML
        [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
        elements. It defines a block-level box.

    [`flex`](#flex)

    :   The element behaves like a block-level element and lays out its
        content according to the [flexbox
        model](css_flexible_box_layout).

    [`grid`](#grid)

    :   The element behaves like a block-level element and lays out its
        content according to the [grid
        model](css_grid_layout/basic_concepts_of_grid_layout).

    [`ruby`](#ruby) [Experimental]

    :   The element behaves like an inline-level element and lays out
        its content according to the ruby formatting model. It behaves
        like the corresponding HTML
        [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby)
        elements.

**Note:** Browsers that support the multi-keyword syntax, on finding the
inner value only, such as when `display: flex` or `display: grid` is
specified, will set their outer value to `block`. This will result in
expected behavior; for example, if you specify an element to be
`display: grid`, you would expect that the box created on the grid
container would be a block-level box.

### List Item

[`<display-listitem>`](display-listitem.md)

:   The element generates a block box for the content and a separate
    list-item inline box.

A single value of `list-item` will cause the element to behave like a
list item. This can be used together with
[`list-style-type`](list-style-type.md) and
[`list-style-position`](list-style-position.md).

`list-item` can also be combined with any
[`<display-outside>`](display-outside.md) keyword and the `flow` or
`flow-root` [`<display-inside>`](display-inside.md) keywords.

**Note:** In browsers that support the multi-keyword syntax, if no inner
value is specified, it will default to `flow`. If no outer value is
specified, the principal box will have an outer display type of `block`.

### Internal

[`<display-internal>`](display-internal.md)

:   Some layout models such as `table` and `ruby` have a complex
    internal structure, with several different roles that their children
    and descendants can fill. This section defines those \"internal\"
    display values, which only have meaning within that particular
    layout mode.

    [`table-row-group`](#table-row-group)

    :   These elements behave like
        [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody)
        HTML elements.

    [`table-header-group`](#table-header-group)

    :   These elements behave like
        [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead)
        HTML elements.

    [`table-footer-group`](#table-footer-group)

    :   These elements behave like
        [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot)
        HTML elements.

    [`table-row`](#table-row)

    :   These elements behave like
        [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)
        HTML elements.

    [`table-cell`](#table-cell)

    :   These elements behave like
        [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)
        HTML elements.

    [`table-column-group`](#table-column-group)

    :   These elements behave like
        [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup)
        HTML elements.

    [`table-column`](#table-column)

    :   These elements behave like
        [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col)
        HTML elements.

    [`table-caption`](#table-caption)

    :   These elements behave like
        [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption)
        HTML elements.

    [`ruby-base`](#ruby-base) [Experimental]

    :   These elements behave like
        [`<rb>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rb)
        HTML elements.

    [`ruby-text`](#ruby-text) [Experimental]

    :   These elements behave like
        [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt)
        HTML elements.

    [`ruby-base-container`](#ruby-base-container) [Experimental]

    :   These elements are generated as anonymous boxes.

    [`ruby-text-container`](#ruby-text-container) [Experimental]

    :   These elements behave like
        [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc)
        HTML elements.

### Box

[`<display-box>`](display-box.md)

:   These values define whether an element generates display boxes at
    all.

    [`contents`](#contents)

    :   These elements don\'t produce a specific box by themselves. They
        are replaced by their pseudo-box and their child boxes. Please
        note that the CSS Display Level 3 spec defines how the
        `contents` value should affect \"unusual elements\" --- elements
        that aren\'t rendered purely by CSS box concepts such as
        replaced elements. See [Appendix B: Effects of display: contents
        on Unusual
        Elements](https://drafts.csswg.org/css-display/#unbox) for more
        details.

    [`none`](#none)

    :   Turns off the display of an element so that it has no effect on
        layout (the document is rendered as though the element did not
        exist). All descendant elements also have their display turned
        off. To have an element take up the space that it would normally
        take, but without actually rendering anything, use the
        [`visibility`](visibility) property instead.

### Precomposed

[`<display-legacy>`](display-legacy.md)

:   CSS 2 used a single-keyword, precomposed syntax for the `display`
    property, requiring separate keywords for block-level and
    inline-level variants of the same layout mode.

    [`inline-block`](#inline-block)

    :   The element generates a block box that will be flowed with
        surrounding content as if it were a single inline box (behaving
        much like a replaced element would).

        It is equivalent to `inline flow-root`.

    [`inline-table`](#inline-table)

    :   The `inline-table` value does not have a direct mapping in HTML.
        It behaves like an HTML
        [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
        element, but as an inline box, rather than a block-level box.
        Inside the table box is a block-level context.

        It is equivalent to `inline table`.

    [`inline-flex`](#inline-flex)

    :   The element behaves like an inline-level element and lays out
        its content according to the flexbox model.

        It is equivalent to `inline flex`.

    [`inline-grid`](#inline-grid)

    :   The element behaves like an inline-level element and lays out
        its content according to the grid model.

        It is equivalent to `inline grid`.

### Which syntax should you use now?

The Level 3 specification details two values for the `display` property
--- enabling the specification of the outer and inner display type
explicitly --- but this is not yet well-supported by browsers.

The precomposed `<display-legacy>` methods allow the same results with
single keyword values, and should be favoured by developers until the
two keyword values are better supported. For example, using two values
you might specify an inline flex container as follows:

[css]

```css
.container {
  display: inline flex;
}
```

This can currently be specified using a single value.

[css]

```css
.container {
  display: inline-flex;
}
```

For more information on these changes to the specification, see the
article [](multi-keyword_syntax_of_display.md).

### Global

[css]

```css
/* Global values */
display: inherit;
display: initial;
display: unset;
```

Description
-----------

The individual pages for the different types of value that `display` can
have set on it feature multiple examples of those values in action ---
see the [Syntax](#syntax) section. In addition, see the following
material, which covers the various values of display in depth.

- [](multi-keyword_syntax_of_display.md)

### CSS Flow Layout (display: block, display: inline)

- [](block_and_inline_layout_in_normal_flow.md)
- [Flow Layout and Overflow](flow_layout_and_overflow.md)
- [](flow_layout_and_writing_modes.md)
- [](introduction_to_formatting_contexts.md)
- [In Flow and Out of Flow](in_flow_and_out_of_flow.md)

### display: flex

- [](basic_concepts_of_flexbox.md)
- [](aligning_items_in_a_flex_container.md)
- [](controlling_ratios_of_flex_items_along_the_main_axis.md)
- [](mastering_wrapping_of_flex_items.md)
- [Ordering Flex Items](ordering_flex_items.md)
- [](relationship_of_flexbox_to_other_layout_methods.md)
- [](typical_use_cases_of_flexbox.md)

### display: grid

- [](basic_concepts_of_grid_layout.md)
- [](relationship_of_grid_layout_with_other_layout_methods.md)
- [](grid_layout_using_line-based_placement.md)
- [Grid template areas](grid_template_areas.md)
- [](grid_layout_using_named_grid_lines.md)
- [](auto-placement_in_grid_layout.md)
- [](_Resources/Markup%20And%20Styling/css/css_grid_layout/box_alignment_in_grid_layout.md)
- [](grids_logical_values_and_writing_modes.md)
- [](grid_layout_and_accessibility.md)
- [](grid_layout_and_progressive_enhancement.md)
- [](realizing_common_layouts_using_grids.md)

Accessibility concerns
----------------------

### display: none

Using a `display` value of `none` on an element will remove it from the
[accessibility
tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis).
This will cause the element and all its descendant elements to no longer
be announced by screen reading technology.

If you want to visually hide the element, a more accessible alternative
is to use [a combination of
properties](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link)
to remove it visually from the screen but keep it parsable by assistive
technology such as screen readers.

### display: contents

Current implementations in some browsers will remove from the
[accessibility
tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis)
any element with a `display` value of `contents` (but descendants will
remain). This will cause the element itself to no longer be announced by
screen reading technology. This is incorrect behavior according to the
[CSS
specification](https://drafts.csswg.org/css-display/#valdef-display-contents).

- [More accessible markup with display: contents \| Hidde de
    Vries](https://hidde.blog/more-accessible-markup-with-display-contents/)
- [Display: Contents Is Not a CSS Reset \| Adrian
    Roselli](https://adrianroselli.com/2018/05/display-contents-is-not-a-css-reset.html)

### Tables

In some browsers, changing the `display` value of a
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
element to `block`, `grid`, or `flex` will alter its representation in
the [accessibility
tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis).
This will cause the table to no longer be announced properly by screen
reading technology.

- [Short note on what CSS display properties do to table semantics ---
    The Paciello
    Group](https://www.tpgi.com/short-note-on-what-css-display-properties-do-to-table-semantics/)
- [Hidden content for better a11y \| Go Make
    Things](https://gomakethings.com/hidden-content-for-better-a11y/)
- [MDN Understanding WCAG, Guideline 1.3
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `inline`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as the specified value, except for positioned and floating elements and the root element. In both cases the computed value may be a keyword other than the one specified.
  Animation type                     Not animatable
  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
display = 
  [ <display-outside> || <display-inside> ]         |
  <display-listitem>                                |
  <display-internal>                                |
  <display-box>                                     |
  <display-legacy>                                  |
  <display-outside> || [ <display-inside> | math ]  

<display-outside> = 
  block   |
  inline  |
  run-in  

<display-inside> = 
  flow       |
  flow-root  |
  table      |
  flex       |
  grid       |
  ruby       

<display-listitem> = 
  <display-outside>?     &&
  [ flow | flow-root ]?  &&
  list-item              

<display-internal> = 
  table-row-group      |
  table-header-group   |
  table-footer-group   |
  table-row            |
  table-cell           |
  table-column-group   |
  table-column         |
  table-caption        |
  ruby-base            |
  ruby-text            |
  ruby-base-container  |
  ruby-text-container  

<display-box> = 
  contents  |
  none      

<display-legacy> = 
  inline-block  |
  inline-table  |
  inline-flex   |
  inline-grid   
```

Examples
--------

### display value comparison

In this example we have two block-level container elements, each one
with three inline children. Below that, we have a select menu that
allows you to apply different `display` values to the containers,
allowing you to compare and contrast how the different values affect the
element\'s layout, and that of their children.

We\'ve included [`padding`](padding.md) and
[`background-color`](background-color.md) on the containers and their
children, so that it is easier to see the effect the display values are
having.

**Note:** We\'ve not included any of the modern multi-keyword syntax, as
support for that is still fairly limited.

#### HTML

[html]

```html
<article class="container">
  <span>First</span>
  <span>Second</span>
  <span>Third</span>
</article>

<article class="container">
  <span>First</span>
  <span>Second</span>
  <span>Third</span>
</article>

<div>
  <label for="display">Choose a display value:</label>
  <select id="display">
    <option selected>block</option>
    <option>inline</option>
    <option>inline-block</option>
    <option>none</option>
    <option>flex</option>
    <option>inline-flex</option>
    <option>grid</option>
    <option>inline-grid</option>
    <option>table</option>
    <option>list-item</option>
  </select>
</div>
```

#### CSS

[css]

```css
html {
  font-family: helvetica, arial, sans-serif;
  letter-spacing: 1px;
  padding-top: 10px;
}

article {
  background-color: red;
}

article span {
  background-color: black;
  color: white;
  margin: 1px;
}

article,
span {
  padding: 10px;
  border-radius: 7px;
}

article,
div {
  margin: 20px;
}
```

#### JavaScript

[js]

```js
const articles = document.querySelectorAll(".container");
const select = document.querySelector("select");

function updateDisplay() {
  articles.forEach((article) => {
    article.style.display = select.value;
  });
}

select.addEventListener("change", updateDisplay);

updateDisplay();
```

#### Result

**Note:** You can find more examples in the pages for each separate
display data type, linked above.

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Display Module Level 3\
  [\#
  the-display-properties]](https://drafts.csswg.org/css-display/#the-display-properties)

  ------------------------------------------------------------------------------------------------

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

`display`

1

12

1

4

7

1

≤37

18

4

10.1

1

1.0

`contents`

65

79

37

No

52

11.1

65

65

37

47

11.3

9.0

`display-outside`

1

12

1

4

7

1

4.4

18

4

10.1

1

1.0

`flex`

2921

12

20Firefox 28 added multi-line flexbox support.

11IE incorrectly positions inline block content inside flex containers.
See the [discussion on Microsoft
Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

8IE incorrectly positions inline block content inside flex containers.
See the [discussion on Microsoft
Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

161512.1--15

97

≤374.4

2925

20Firefox 28 added multi-line flexbox support.

161412.1--14

97

2.01.5

`flow-root`

58

79

53

No

45

13

58

58

53

43

13

7.0

`grid`

57

1612

52

10Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0Samsung Internet added this earlier than the corresponding Chrome
version would indicate.

`inline-block`

1

12

1

8

6Until Internet Explorer 8, `inline-block` is only for natural inline
elements.

7

1

≤37

18

4

14

1

1.0

`inline-flex`

2921

12

20Firefox 28 added multi-line flexbox support.

118

1615

97

≤374.4

2925

20Firefox 28 added multi-line flexbox support.

1614

97

2.01.5

`inline-grid`

57

1612

52

10Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0Samsung Internet added this earlier than the corresponding Chrome
version would indicate.

`inline-table`

1

12

3

8

7

1

≤37

18

4

14

1

1.0

`keyframe_animatable`

116

116

No

No

102

No

116

116

No

No

No

No

`list-item`

1

12

1

6

7

1

≤37

18

4

14

1

1.0

`math`

109

109

No

No

95

No

109

109

No

74

No

21.0

`multi-keyword_values`

115

115

70

No

101

15

115

115

79

No

15

No

`none`

1Chrome 65 stopped creating layout objects for elements inside an
`<iframe>` with `display:none` applied.

12

1

4

7Opera 52 stopped creating layout objects for elements inside an
`<iframe>` with `display:none` applied.

1

≤37WebView 65 stopped creating layout objects for elements inside an
`<iframe>` with `display:none` applied.

18Chrome 65 stopped creating layout objects for elements inside an
`<iframe>` with `display:none` applied.

4

10.1Opera Android 47 stopped creating layout objects for elements inside
an `<iframe>` with `display:none` applied.

1

1.0Chrome 65 stopped creating layout objects for elements inside an
`<iframe>` with `display:none` applied.

`ruby_values`

No

12--79

38

7

No

No

No

No

38

No

No

No

`table_values`

1

12

1

8

7

1

≤37

18

4

14

1

1.0

`transitionable`

117

117

No

No

103

No

117

117

No

No

No

No

See also
--------

- [](block_and_inline_layout_in_normal_flow.md)
- [](introduction_to_formatting_contexts.md)
- [`visibility`](visibility.md), [`float`](float.md), [`position`](position.md)
- [`grid`](_Resources/Markup%20And%20Styling/css/grid.md), [`flex`](flex.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/display>
