Box-shadow generator
====================

This tool lets you construct CSS [`box-shadow`](box-shadow.md) effects,
to add box shadow effects to your CSS objects.

The box-shadow generator enables you to add one or more box shadows to
an element.

On opening the tool, you\'ll find a rectangle in the top-right section
of the tool. That\'s the element you\'re going to be applying shadows
to. When this element is selected (as it is, when you first load the
page) you can apply some basic styling to it:

- Set the element\'s [`color`](_Resources/Markup%20And%20Styling/css/color.md) using the color picker tool.
- Give the element a [`border`](border.md) using the \"border\"
    checkbox.
- Use the sliders to set the element\'s [`top`](top.md),
    [`left`](left.md), [`width`](_Resources/Markup%20And%20Styling/css/width.md), and [`height`](_Resources/Markup%20And%20Styling/css/height.md)
    properties.

To add a box shadow, click the \"+\" button at the top-left. This adds a
shadow, and lists it in the column on the left. Now you can set the
values of the new shadow:

- Set the shadow\'s [`color`](_Resources/Markup%20And%20Styling/css/color.md) using the color picker tool.
- Set the shadow to be inset using the \"inset\" checkbox.
- Use the sliders to set the element\'s position, blur, and spread.

To add another shadow, click \"+\" again. Now any values you set will
apply to this new shadow. Change the order in which these two shadows
are applied using the ↑ and ↓ buttons at the top-left. Select the first
shadow again by clicking it in column on the left. To update the
element\'s own styles, select it by clicking the button labelled
\"element\" along the top.

You can add [`::before`](../::before) and [`::after`](../::after)
pseudo-elements to the element, and give them box shadows as well. To
switch between the element and its pseudo-elements, use the buttons
along the top labeled \"element\", \":before\", and \":after\".

The box at the bottom-right contains the CSS for the element and any
`before::` or `::after` pseudo-elements.

See also
--------

[Border-image generator](border-image_generator.md)

:   This interactive tool lets you visually create border images (the
    [`border-image`](border-image.md) property).

[Border-radius generator](border-radius_generator.md)

:   This interactive tool lets you visually create rounded corners (the
    [`border-radius`](border-radius.md) property).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders/Box-shadow_generator>
