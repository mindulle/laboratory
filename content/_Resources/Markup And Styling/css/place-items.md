place-items
===========

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
`place-items` [shorthand property](shorthand_properties.md) allows you to
align items along both the block and inline directions at once (i.e. the
[`align-items`](align-items.md) and [`justify-items`](justify-items.md)
properties) in a relevant layout system such as [Grid](css_grid_layout.md)
or [Flexbox](css_flexible_box_layout.md). If the second value is not set,
the first value is also used for it.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`align-items`](align-items.md)
- [`justify-items`](justify-items.md)

Syntax
------

[css]

```css
/* Keyword values */
place-items: center;
place-items: normal start;

/* Positional alignment */
place-items: center normal;
place-items: start legacy;
place-items: end normal;
place-items: self-start legacy;
place-items: self-end normal;
place-items: flex-start legacy;
place-items: flex-end normal;

/* Baseline alignment */
place-items: baseline normal;
place-items: first baseline legacy;
place-items: last baseline normal;
place-items: stretch legacy;

/* Global values */
place-items: inherit;
place-items: initial;
place-items: revert;
place-items: revert-layer;
place-items: unset;
```

### Values

One of the following forms:

- A single [`align-items`](align-items.md) value, which is used to set
    alignment in both block and inline directions.
- An [`align-items`](align-items.md) value, which sets alignment in the
    block direction, followed by a [`justify-items`](justify-items.md)
    value, which sets alignment in the inline direction.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`align-items`](align-items.md): |
|                                   |     `normal`                      |
|                                   | -                                 |
|                                   | [`justify-items`](justify-items.md): |
|                                   |     `legacy`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`align-items`](align-items.md): |
|                                   |     as specified                  |
|                                   | -                                 |
|                                   | [`justify-items`](justify-items.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | discrete                          |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
place-items = 
  <'align-items'> <'justify-items'>?  
```

Examples
--------

### Placing items in a flex container

In flexbox [`justify-self`](justify-self.md) or
[`justify-items`](justify-items.md) do not apply, as on the main axis items
are treated as a group. Therefore, the second value will be ignored.

#### CSS

[css]

```css
#container {
  height: 200px;
  width: 240px;
  place-items: stretch; /* You can change this value by selecting another option in the list */
  background-color: #8c8c8c;
  display: flex;
}
```

#### Result

### Placing items in a grid container

The following grid container has items which are smaller than the grid
areas they are placed in, therefore `place-items` will move them in the
block and inline dimensions.

#### CSS

[css]

```css
#gridcontainer {
  height: 200px;
  width: 240px;
  place-items: stretch; /* You can change this value by selecting another option in the list */
  background-color: #8c8c8c;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

#gridcontainer > div {
  width: 50px;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\#
  place-items-property]](https://drafts.csswg.org/css-align/#place-items-property)

  ------------------------------------------------------------------------------------------

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

`place-items`

59

79

45

No

46

11

59

59

45

43

11

7.0

`flex_context`

59

79

45

No

46

11

59

59

45

43

11

7.0

`grid_context`

59

79

45

No

46

11

59

59

45

43

11

7.0

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](aligning_items_in_a_flex_container.md)*
- CSS Grid Guide: *[](_Resources/Markup%20And%20Styling/css/css_grid_layout/box_alignment_in_grid_layout.md)*
- [CSS Box Alignment](css_box_alignment.md)
- The [`align-items`](align-items.md) property
- The [`align-self`](align-self.md) property
- The [`justify-items`](justify-items.md) property
- The [`justify-self`](justify-self.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/place-items>
