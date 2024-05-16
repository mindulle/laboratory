Value definition syntax
=======================

**CSS value definition syntax**, a formal grammar, is used for defining
the set of valid values for a CSS property or function. In addition to
this syntax, the set of valid values can be further restricted by
semantic constraints (for example, for a number to be strictly
positive).

The definition syntax describes which values are allowed and the
interactions between them. A component can be a *keyword*, some
characters considered as a *literal*, or a value of a given CSS data
type or of another CSS property.

Component value types
---------------------

### Keywords

#### Generic keywords

A keyword with a predefined meaning appears literally, without quotation
marks. For example: `auto`, `smaller` or `ease-in`.

#### The specific case of `inherit`, `initial` and `unset`

All CSS properties accept the keywords `inherit`, `initial` and `unset`,
that are defined throughout CSS. They are not shown in the value
definition, and are implicitly defined.

### Literals

In CSS, a few characters can appear on their own, like the slash
(\'`/`\') or the comma (\'`,`\'), and are used in a property definition
to separate its parts. The comma is often used to separate values in
enumerations, or parameters in mathematical-like functions; the slash
often separates parts of the value that are semantically different, but
have a common syntax. Typically, the slash is used in shorthand
properties; to separate components that are of the same type, but belong
to different properties.

Both symbols appear literally in a value definition.

### Data types

#### Basic data types

Some kind of data are used throughout CSS, and are defined once for all
values in the specification. Called *basic data types*, they are
represented with their name surrounded by the symbol \'`<`\' and
\'`>`\': [`<angle>`](angle.md), [`<string>`](string.md), ...

#### Non-terminal data types

Less common data types, called *non-terminal data types*, are also
surrounded by \'`<`\' and \'`>`\'.

Non-terminal data types are of two kinds:

- data types *sharing the same name of a property*, put between
    quotes. In this case, the data type shares the same set of values as
    the property. They are often used in the definition of shorthand
    properties.
- data type *not sharing the same name of a property*. These data
    types are very close to the basic data types. They only differ from
    the basic data types in the physical location of their definition.
    In this case, the definition is usually physically very close to the
    definition of the property using them.

Component value combinators
---------------------------

### Brackets

*Brackets* enclose several entities, combinators, and multipliers, then
transform them as a single component. They are used to **group
components to bypass the precedence rules**.

[css]

```css
bold [ thin && <length> ]
```

This example matches the following values:

- `bold thin 2vh`
- `bold 0 thin`
- `bold thin 3.5em`

But not:

- `thin bold 3em`, as `bold` is juxtaposed with the component defined
    by the brackets, it must appear before it.

### Juxtaposition

Placing several keywords, literals or data types, next to one another,
only separated by one or several spaces, is called *juxtaposition*. All
juxtaposed components are **mandatory and should appear in the exact
order**.

[css]

```css
bold <length>, thin
```

This example matches the following values:

- `bold 1em, thin`
- `bold 0, thin`
- `bold 2.5cm, thin`
- `bold 3vh, thin`

But not:

- `thin 1em, bold`, as the entities must be in the expressed order
- `bold 1em thin`, as the entities are mandatory; the comma, a
    literal, must be present
- `bold 0.5ms, thin`, as the `ms` values are not [`<length>`](length.md)

### Double ampersand

Separating two or more components, by a *double ampersand*, `&&`, means
that all these entities are **mandatory but may appear in any order**.

[css]

```css
bold && <length>
```

This example matches the following values:

- `bold 1em`
- `bold 0`
- `2.5cm bold`
- `3vh bold`

But not:

- `bold`, as both components must appear in the value.
- `bold 1em bold`, as both components must appear only one time.

**Note:** juxtaposition has precedence over the double ampersand,
meaning that `bold thin && <length>` is equivalent to
`[ bold thin ] && <length>`. It describes `bold thin <length>` or
`<length> bold thin` but not `bold <length> thin`.

### Double bar

Separating two or more components by a *double bar*, `||`, means that
all entities are options: **at least one of them must be present, and
they may appear in any order**. Typically this is used to define the
different values of a [shorthand property](shorthand_properties.md).

[css]

```css
<'border-width'> || <'border-style'> || <'border-color'>
```

This example matches the following values:

- `1em solid blue`
- `blue 1em`
- `solid 1px yellow`

But not:

- `blue yellow`, as a component must appear at most one single time.
- `bold`, as it isn\'t a keyword allowed as value of any of the
    entity.

**Note:** the double ampersand has precedence over the double bar,
meaning that `bold || thin && <length>` is equivalent to
`bold || [ thin && <length> ]`. It describes `bold`, `thin <length>`,
`bold thin <length>`, or `thin <length> bold` but not
`<length> bold thin` as bold, if not omitted, must be placed before or
after the whole `thin && <length>` component.

### Single bar

Separating two or more entities by a *single bar*, `|`, means that all
entities are exclusive options: **exactly one of these options must be
present**. This is typically used to separate a list of possible
keywords.

[css]

```css
<percentage> | <length> | left | center | right | top | bottom
```

This example matches the following values:

- `3%`
- `0`
- `3.5em`
- `left`
- `center`
- `right`
- `top`
- `bottom`

But not:

- `center 3%`, as only one of the components must be present.
- `3em 4.5em`, as a component must be present at most one time.

**Note:** the double bar has precedence over the single bar, meaning
that `bold | thin || <length>` is equivalent to
`bold | [ thin || <length> ]`. It describes `bold`, `thin`, `<length>`,
`<length> thin`, or `thin <length>` but not `bold <length>` as only one
entity from each side of the `|` combinator can be present.

Component value multipliers
---------------------------

A multiplier is a sign that indicates how many times a preceding entity
can be repeated. Without a multiplier, an entity must appear exactly one
time.

Note that multipliers cannot be added and have precedence over all
combinators.

### Asterisk (`*`)

The *asterisk multiplier* indicates that the entity may appear **zero,
one or several times**.

[css]

```css
bold smaller*
```

This example matches the following values:

- `bold`
- `bold smaller`
- `bold smaller smaller`
- `bold smaller smaller smaller`, and so on.

But not:

- `smaller`, as `bold` is juxtaposed, and must appear before any
    `smaller` keyword.

### Plus (`+`)

The *plus multiplier* indicates that the entity may appear **one or
several times**.

[css]

```css
bold smaller+
```

This example matches the following values:

- `bold smaller`
- `bold smaller smaller`
- `bold smaller smaller smaller`, and so on.

But not:

- `bold`, as `smaller` must appear at least one time.
- `smaller`, as `bold` is juxtaposed and must appear before any
    `smaller` keyword.

### Question mark (`?`)

The *question mark multiplier* indicates that the entity is optional,
and **must appear zero or one time**.

[css]

```css
bold smaller?
```

This example matches the following values:

- `bold`
- `bold smaller`

But not:

- `bold smaller smaller`, as `smaller` must appear at most one time.
- `smaller`, as `bold` is juxtaposed and must appear before any
    `smaller` keyword.

### Curly braces (``)

The *curly braces multiplier*, enclosing two integers separated by a
comma, A and B, indicates that the entity **must appear at least A times
and at most B times**.

[css]

```css
bold smaller
```

This example matches the following values:

- `bold smaller`
- `bold smaller smaller`
- `bold smaller smaller smaller`

But not:

- `bold`, as `smaller` must appear at least one time.
- `bold smaller smaller smaller smaller`, as `smaller` must appear at
    most three times.
- `smaller`, as `bold` is juxtaposed and must appear before any
    `smaller` keyword

### Hash mark (`#`)

The *hash mark multiplier* indicates that the entity may be repeated one
or more times (for example, the plus multiplier), but each occurrence is
separated by a comma (\',\').

[css]

```css
bold smaller#
```

This example matches the following values:

- `bold smaller`
- `bold smaller, smaller`
- `bold smaller, smaller, smaller`, and so on.

But not:

- `bold`, as `smaller` must appear at least one time.
- `bold smaller smaller smaller`, as the different occurrences of
    `smaller` must be separated by commas.
- `smaller`, as `bold` is juxtaposed and must appear before any
    `smaller` keyword.

The hash mark may optionally be followed by curly braces to indicate
precisely how many times the repetition occurs.

[css]

```css
bold smaller#
```

This example matches the following values:

- `bold smaller`
- `bold smaller, smaller`
- `bold smaller, smaller, smaller`

But not:

- `bold smaller, smaller, smaller, smaller`, as `smaller` must appear
    at most three times.

[css]

```css
bold smaller#
```

This example matches the following value:

- `bold smaller, smaller`

But not:

- `bold smaller`, as `smaller` must appear exactly two times.

### Exclamation point (`!`)

The *exclamation point multiplier* after a group indicates that the
group is required, and must produce at least one value; even if the
grammar of the items within the group would otherwise allow the entire
contents to be omitted, at least one component value must not be
omitted.

[css]

```css
[ bold? smaller? ]!
```

This example matches the following values:

- `bold`
- `smaller`
- `bold smaller`

But not:

- neither `bold` nor `smaller`, as one of them must appear.
- `smaller bold`, as `bold` is juxtaposed and must appear before the
    `smaller` keyword.
- `bold smaller bold`, as `bold` and `smaller` may only appear once.

Summary
-------

Sign

Name

Description

Example

Combinators

Juxtaposition

Components are mandatory and should appear in that order

`solid <length>`

`&&`

Double ampersand

Components are mandatory but may appear in any order

`<length> && <string>`

`||`

Double bar

At least one of the components must be present, and they may appear in
any order.

`<'border-image-outset'> || <'border-image-slice'>`

`|`

Single bar

Exactly one of the components must be present

`smaller | small | normal | big | bigger`

`[ ]`

Brackets

Group components to bypass precedence rules

`bold [ thin && <length> ]`

Multipliers

No multiplier

Exactly 1 time

`solid`

`*`

Asterisk

0 or more times

`bold smaller*`

`+`

Plus sign

1 or more times

`bold smaller+`

`?`

Question mark

0 or 1 time (that is *optional)*

`bold smaller?`

``

Curly braces

At least `A` times, at most `B` times

`bold smaller`

`#`

Hash mark

1 or more times, but each occurrence separated by a comma (\'`,`\')

`bold smaller#`

`!`

Exclamation point

Group must produce at least 1 value

`[ bold? smaller? ]!`

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  value-defs]](https://drafts.csswg.org/css-values/#value-defs)

  -----------------------------------------------------------------------

See also
--------

- CSS key concepts:
  - [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
  - [Comments](comments.md)
  - [Specificity](specificity.md)
  - [Inheritance](inheritance.md)
  - [Box model](introduction_to_the_css_box_model.md)
  - [Layout modes](layout_mode.md)
  - [Visual formatting models](visual_formatting_model.md)
  - [Margin collapsing](mastering_margin_collapsing.md)
  - Values
    - [Initial values](initial_value.md)
    - [Computed values](computed_value.md)
    - [Used values](used_value.md)
    - [Actual values](actual_value.md)
  - **Value definition syntax**
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Value_definition_syntax>
