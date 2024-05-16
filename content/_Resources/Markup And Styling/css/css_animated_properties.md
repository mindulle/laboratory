Animatable CSS properties
=========================

[CSS Animations](css_animations.md) and [Transitions](css_transitions.md) rely
on the concept of **animatable** properties, and all CSS properties are
animatable unless otherwise specified. Each property\'s *animation type*
determines how values
[combine](https://drafts.csswg.org/css-values/#combining-values) -
interpolate, add, or accumulate - for this property. Transitions only
involve interpolation, whereas animations may use all three combination
methods.

**Note:** The animation type for each CSS property is listed in its
\"Formal definition\" table (E.g., [`color`](_Resources/Markup%20And%20Styling/css/color.md#formal_definition)).

**Note:** The interpolation method for each CSS data type is described
in its \"Interpolation\" section (E.g.,
[`<length>`](length.md#interpolation)).

Animation types
---------------

There are mainly four animation types as defined in the [Web
Animations](https://drafts.csswg.org/web-animations-1/#animating-properties)
specification:

[Not animatable](#not_animatable)

:   The property is not animatable. It is not processed when listed in
    an animation keyframe and is unaffected by transitions.

    **Note:** An animation effect targeting only properties that are not
    animatable will still exhibit the usual behavior for an animation
    effect (E.g., firing the
    [`animationstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationstart_event)
    event).

[Discrete](#discrete)

:   The property\'s values are not additive, and interpolation swaps
    from the start value to the end value at `50%`. Specifically,
    denoting by `p` the progress value:

    -   If `p < 0.5`, then `V_result = V_start`;
    -   If `p ≥ 0.5`, then `V_result = V_end`.

[By computed value](#by_computed_value)

:   Corresponding individual components of the computed values are
    combined using the indicated procedure for that value type. If the
    number of components or the types of corresponding components do not
    match, or if any component value uses discrete animation and the two
    corresponding values do not match, then the property values combine
    as discrete.

[Repeatable list](#repeatable_list)

:   Same as by computed value except that if the two lists have
    differing numbers of items, they are first repeated to the least
    common multiple numbers of items. Each item is then combined by
    computed value. If a pair of values cannot be combined or any
    component value uses discrete animation, then the property values
    combine as discrete.

Some properties have specific interpolation behavior not covered by
these four types. In this case, refer to the property\'s
\"Interpolation\" section (E.g.,
[`visibility`](visibility.md#interpolation)).

Animating custom properties
---------------------------

For custom properties registered using the
[`registerProperty()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/registerProperty_static)
method, the animation type is by computed value, with the computed value
type
[determined](https://drafts.css-houdini.org/css-properties-values-api/#calculation-of-computed-values)
by the property\'s syntax definition.

For unregistered custom properties, the animation type is discrete.

See also
--------

- [Using CSS Animations](using_css_animations.md)
- [Using CSS Transitions](using_css_transitions.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties>
