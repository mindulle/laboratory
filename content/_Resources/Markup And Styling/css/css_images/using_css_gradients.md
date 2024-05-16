Using CSS gradients
===================

**CSS gradients** are represented by the [`<gradient>`](gradient.md)
data type, a special type of [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) made of a progressive
transition between two or more colors. You can choose between three
types of gradients: *linear* (created with the
[`linear-gradient()`](linear-gradient.md) function), *radial*
(created with the [`radial-gradient()`](radial-gradient.md)
function), and *conic* (created with the
[`conic-gradient()`](conic-gradient.md) function). You can also
create repeating gradients with the
[`repeating-linear-gradient()`](repeating-linear-gradient.md),
[`repeating-radial-gradient()`](repeating-radial-gradient.md),
and [`repeating-conic-gradient()`](repeating-conic-gradient.md)
functions.

Gradients can be used anywhere you would use an `<image>`, such as in
backgrounds. Because gradients are dynamically generated, they can
negate the need for the raster image files that traditionally were used
to achieve similar effects. In addition, because gradients are generated
by the browser, they look better than raster images when zoomed in, and
can be resized on the fly.

We\'ll start by introducing linear gradients, then introduce features
that are supported in all gradient types using linear gradients as the
example, then move on to radial, conic and repeating gradients

Using linear gradients
----------------------

A linear gradient creates a band of colors that progress in a straight
line.

### A basic linear gradient

To create the most basic type of gradient, all you need is to specify
two colors. These are called *color stops*. You must have at least two,
but you can have as many as you want.

[css]

```css
.simple-linear {
  background: linear-gradient(blue, pink);
}
```

### Changing the direction

By default, linear gradients run from top to bottom. You can change
their rotation by specifying a direction.

[css]

```css
.horizontal-gradient {
  background: linear-gradient(to right, blue, pink);
}
```

### Diagonal gradients

You can even make the gradient run diagonally, from corner to corner.

[css]

```css
.diagonal-gradient {
  background: linear-gradient(to bottom right, blue, pink);
}
```

### Using angles

If you want more control over its direction, you can give the gradient a
specific angle.

[css]

```css
.angled-gradient {
  background: linear-gradient(70deg, blue, pink);
}
```

When using an angle, `0deg` creates a vertical gradient running bottom
to top, `90deg` creates a horizontal gradient running left to right, and
so on in a clockwise direction. Negative angles run in the
counterclockwise direction.

![Four boxes listing angle and showing associated gradient from red to white. 0deg starts at the bottom and goes up. 90deg starts at left and goes right. 180deg starts at the top and goes down. -90deg starts at
right and goes left.](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAegAAAB6CAMAAABDVzDCAAACKFBMVEX////4xMLwSjnwUEHwTj7wQizwQSsAAADwPyfwQCnwRTHxUkTwQy773dz3vbvwPibzhH3xX1T2qqbydW3xVUfxWUvwSDX619bxXVL1nJj0mpbziIL1p6P3trP0mZT4wr/+9/f97ez84+P98vH3urjyb2bwTDv2sa75ycfxY1j2rar5ysjxWk7xZFr4v73wRzTyd2/wPifye3T++vr61NPxZ133uLb+9fX4x8XyeXH85OT1paHwSTjzhoDzgHrzjIfwPSXyc2vwRjP2sK3zgnvxV0nxZlvya2L/+/v1o6D1oZ30j4r86un//v750tD0ko3wRDD5zcvzfXbxYVb50M797+73tLH85ub0k47zf3nycGj0lpH5zszxW0/ybWT1n5v62djycWn0jon0kYvybGPwTT3zi4X629rwUkP609LxXFDxVEbyenP74N/1o5/xaWD0lZDxaV/62Nf99PP1npr74eD2s7D98/L97u32r6z739774uH2rKj86Of+9vb86ej4w8DhPypHCwSSJxTFNiMABA4AFDaYOSMvDQzWXUNOUmgAByNbOjXhbVviioYAHmGqLh/XjFsoQ2CrV0qFUkTfd3FmGgt6JBfJTjAEKkefd3bCXFPpupIAPITmnJpdIB/t5eSkRjP61763b2m0h42+nJyIZGjO3eiLjp+XuNNJdp3AsbSflJ3WpIBjjrTi3eD3y6zr19fve2Xlzc32pZX1wJyKn7vuw5uCLIcwAAASuElEQVR42uxa+VcTWRaWQHgsQcUFG7VpQINCWgEFlaW1RQZFaRZpmgZRQQghToMK0iCOtlXZ90ACCbussri2zsy/N/fVklSRpFJED8MP+U6l7qtb7yWn8uUu797s2RNFFFFEEUUUUUQRRRRRRBFFFFFEEUUooB1B9JP/35+8B93YAQR/6H2FCQmJifHxUll9UkV+WrkkJy42tif50D8O/3j3u9TG3DPFj6533WvtOFhQcu52y+X9+491X7nV+fvjjKPpT29Wlx0/kPfs1J/fX7iw9+wPMZcuKRp+rS060q5K6c0ubf4rq+nEwMXMG7+E+OQdQPBP/uXG+cyLJ5qyal6UZj8fSWk/UlT7a1vD6UsxP+zde/LC97+dupZ34HhZ38376Ucz7tR13rrSfeyn/ZWXb/9RcvDg1Vb5va7iqjO5janf3f3x8KF/JsfGxsXlSMrT8iuS6mVSaXxiYkLhvp9DEH1+ByBItNRPtDKOT/STR/fkHVdZon+iib7jJzrv2m/fXzi5hehBhuihl5nnQ/zECinsK6QpgQEPWM/qto6584XXCxE9nPXXi+bswd6UfopoBSb6LE30MyC6uu/mU4roWw8Yos+VlBQc7OhgiE7lEK3MkUgonmXS+PjEBAGiM/14mfkSjkxRCDY35Hphi5axRCvjWKIfMkRf7/IRXckSjS36PkM0tmiK6BhMtNpn0TW0RZ8PYdEJO4AwFt0MFs0Q3dDAIZpv0Q98Fl0AFt0h77oORDeCRT+kiO5hLLoiKSk80Rd3AGItGohO5hL96FGXvPUqz3XXMUT3Ua772p8ci27DFp3CED1Mue4bu5PoYY7rVjMWHaHrVtJE14d33UM0BoYG4AgcU2haWXuDlQMDM6v/GQoKofUDoSJlANGxXKJTFwzTmOiuBfc4bdE262pn3R2fRf+LY9GnGdedQrluyqJfhrToRCEQGoKSTo0Ti0INc51ITHgSEkUjXIxuxkT3H1Fji1bwXHe6a3UFu+5O16qdJtpkdQu4bojRSUyMFrLoE8HRdKIJDmbsQlbLG0o5Q842nRAD3nqRFq1Ucl13KmmZ0LnkHV2kntSPUzHaRk7a+a6bE6PbxLtuIYImENLS0oMmQJKIRBTThQQz+DZEc5IxBc91p5N6q2U5/WgnPPeknSLaBl9AaNctyc+nXHcYoptoDDcNU4CBD1iHrxfRepN7g9aNzoIy69MH6gY7Icz6MERTMTotIBkjLNPFmkl5q9cyLjeuXq7ErtvkAKIf2+eebiWatmg1N+seCk10vAAIAmmxgLMWEfDSJho1zC24xhPixUCkRWPXzc26n+WN6le+aMbSj5r09krjFO26TZhouc1273pQi/a5biGis8JjxvEma3S2JmvRjcxWkB/hVz/2BvRWtOaGe2EhcnvFT8a0FtsTr94mN4wVFGjGWir/9iDrBFj0NOwUzff7ykYn0KpBv8nJusGi+/kxOgTRUh7iIY2BEzsGimEApEqBaKnGKKVehAeREzqsQ4gkpFKtEWlIuA5cz4xDEv2SjdGDI0zW3cDLuk2OuWp4ZRjMdd0ac/cx6rn14wUm+GTro+IzXqPFQOoPHz6UjC2aIRq77jDJWE14AMk1M46aRXJscwrNgtz4sOh2vP4v2th0o/ci3kAwRvuz7hxlLIfoOJ0r1wNEa4Bow1jL3+TkkgtN2m1oKmOUNFePIvOyAW1ws26/RdcIW7SfZBn4EwwYsACisR+c0HmQB5Mso4gmdVon0oG5awiCNALfGi0Jv4gg6ymdVCbConuDJmOj4Lc9QLTGXHfLYO5mnnvchNxyEzlWrNUZXKRlmruPzs+vqJeFTcZK/WgubaYAA67uxajjdfOM4zWI0tLR2dczyDw1BUF7dKO0eXBiPez65tKIsu5UA/yEaaJLDGPgvezHur0OuwG53W7SMWcaO5B3fGItaDL2IkwyJhMCRbQMmNWgeZkMiJY5jTKtjpDhkwZ5PNiSNR6YiHUhITbr9hVMlszwYOaVvC8L8Nx+orEHv+zVjxuQwQCWbNNYcxtzLCbuPlqc684OjxnHh2wgGIjOxvKd5e3KyubmaxhmL5LrIt5ge8nYIbZgkpsLMZp13V6K6Em7YXJpaWppuc/kOJ73hVzjJGNtajW3YCKQjNULAYjGZx1BvTTGevwCjuvxSaNzOp1arUwzT08JDVHJGKdgctJlxXgL2ysgeSwdu+5b4Lq9LNF6l8s1PV2FiSYsprvcfbSoZOz54ODzwedw+CUGHmNgsUi+X5x4/3wGbXx+Z3R8+Ijeq2rfmd98NI5NkWidWiSwHsbb3l7RRKcadNPyDpNuyYSmWmzIPD5t1NtNlqkMu8s812mcXCXR2tbKWAqTjA0LEZ0kAEKLnAQI5Exy6ggsCWQAMU9ojTot3KwnnCRMmteAJxd4nzAxupmJ0Wp1QGWsLGPBspJ+1GZZhjDVzTz3uNfiarUtWG1eNG9AemzRyZzKmIiCSe+ID70jvXDQEmOEvfcOkq8PlNCT6H3vDAmDNdXIx1XzW3LdNyvk+l4RWTfruv0xOhYhC95Hd4ALN99uuQzJiIVE5k4XeLbJ5eqyx27rlM+iYxii+1W+ffTQy5DJWEVo1MOzAYMVSRqQhoqKJCdC86CnkjBkxJdIB3qtZ14D00IjXGWMKoEyrlvBy7rhy12GffRjcOHm7ivH6OceO4g9ut5VXOX1zBu2uO58tgQqFKNTxKDtMz6rij6r4KxKUX3+lDJC3fhoXBexXLRFc2N0o8nElEBt41QJtHKcqozd+d2ewRRM0o1vAy2aQ3Qoi84Ph7T8fAlBENSYEbRMS8MyjVboCIG3ECC6aTiI6/YlY2Vzc9V0Zcxup0qgLeO3z+HKmNzW1UVvr7wM0Yzrzq8QUzBpV6naVe1wqEKBvtnOkRgw+LfRiGY/UXqh9SqVWItWbuleYaJbtzY16O5VX1knfLpjhkc0Zx8t6LrTREFSXk4JCXPJk1qw73mh1eEtmkf02bN7L3CaGvf9TY39uKmBa90ddAnUqyOR9SEn65aIi9H9/f3t/e1w+CUXPAV3IowWV95ufgq/vr1f2KIZoiVbXHfumaon1++Fbmp8WZpa9nWvYnBljFvrFsy6y4NCUi6Bo1wQvjmE06AVXB8+66a7V4Ex+nhZNdu9YmvdQLSvBGpaWJgO6F6J2Ecf+Qqo1UVFYubttn605OuRk5ODv+PQ2G4/mtO9qvZ3r7pZopmmBlsZe3h32/3ookCoi4BBNSvVfoVI8NeDYrf1o3OCQpmjhCPweqs+FPjzIuxHX6MtOrBNWcAnevv96Fq1ulZd64OaucYSg70XTi+4frf1o+MCoIyDTbySLzG4OiEErt91/ei20Ghoa4AjcCwWvjW7rR9NkxMLkQJOAWPu9VY9F8LrI+xHP6OJfsrvRwe47gj60Q0KCg2KBjhoiaHg6Nlrdg4L7rXg+sj60VVV3Kybsei6b9GPjt0BRN6P9rtu/1+J/ijxu+7Gxoj60acVitOK0xQUnHGw62B6hZj1EfWjKdcdJEZ/g350T09yTzIcPRTYcTjdduYm92y3H835h0l1QIwOTMa234++tAOIqB/NEM1YNN2P3pJ1R9qPTt4BbLcffTaY6/bHaNqiu8L8lUiI6JgdQET9aDYZ6+C67gf8GH2KG6PF96MP7QC224/e6y+YlPG2V/tZi+5obaUtGhN9d9v96FevXsW8ioHjFQ9c3Vffj6gfzRRMWv/X3rn4VHFEcTg+o6ZQikqf1tZKfRThVoNiQaggr6KhBUQEL3qBKLFVwDcJ6r/eM7N39s7Ozsw+Gs/80uyXiXPmzJwQXbl37357d7xn3YulfPR4Lk6Mn6A2XpKiPlq/3Td1wST6jW5YTsby++je0056T/dSS8e2eW99ubPuCf0S6HDzPXp2acX68aqQjz7JQGEfbXnpnrFfMDFeunP66PbemPbedmr5YtELevPUl/TR/cmzbvEevba+tLKivUe/KeWje7yc7DlJrac0UX1RH93uu2CiDvSG7WQsp49uZ6Ckj56wXDCZjaWGeaAL+Oh6zNP60wSUSOTFWMSq19f46wv66PxSIz7QBX30WQZK+ejUBRN5MrY+q71H7yavjOX20V8xUNRH55YalpfuXD76FAOlfHTzgknqN9p6waSYj/6CgaI+uozUKOSjFxn4JD7a8tKd10fPM1DQR5eVGvl99DkGPomPlr/R5Xz0BQaK+uh277cp5efoRutkrF4v7KPHxsZ2x3ZjaCDHqtfRcyJWZNaj+ehLkolLExIKUog5W95c466H+370RQbQfHS/ZKI/OlAUJBB5M2db76+H+350556kc69TstccK0R+r9Me6+u99Wg+emdna2eL2k4h9Jrsejgf3ckAmo/e2prcmpRQEMc+9HWuOAmcj/6OATQfvbq6sbohoUDGZm8i8gJzjbsezkdPDw5OD05TG5So2MwJBnOuTeXQfHS3k9XuVWrdpWnVw/no6BhOP59+LqFAxqp35VR+Ok89mo9eTtBYblBLj/W8uSa7Hs5Hv3ooefXwFbWHVtScuUYfe+vRfPRNJ42bDWo3S9Oqh/PRXzOA5qOPMwDno79hAM1H1xiA89HfM4Dmo68zAOejVxhA89GXGYDz0Usttpe2qbX6Jcuca+ytR/PRcwzA+ehZBtB89PDw/eH7uaCFqbW2XBo4Hz2zvj6zPiNZb8aiV6ix2Ztz3no0H31LMnxrmFrU66ic2as5hb8ezkevtZhZm6G2lsDM2dZk1qP56A4G4Hz0yMjI45HH1EZyYVubWY/mozs6bnTciKGBROREbM7pY1vOXg/no79lAM1Hh/s7B/TRN/z/fYvgrEfz0SMMwPnocO9X4Xx0dOogEKcUKvahr3PFSeB89C0G0Hz07Oz6bPShgAIZm71CzwvMNe56OB89bEd8UBQfGM04L4l6NB+9xACcj25+vp+7H13QoSBG5NRYj11jZz2aj95OsLK9Qi091vPmmux6OB9tXKKduzxHzT125bz1aD46nMgJ6KP/YQDNR4dTswF9dI0+ol2PFCoFEjG+Xkv2al7lzHXeejQfHe5mi4A++nitdryWvDmi1szVtLk8sbMezUcn74wSvcC8K0rP2+6a8tfD+ejmTU4NrReoG6f0m6hsN1Q18tSj+eg/GIDz0Y7bHwX6LZBq7FrjrUfz0f6bV/U5102x2fVwPjrjRuXl7mVq5W90lvVoPnqQATgfrX3FoCjmVxScoPnocN9OCeijJycnNyY3qLV6HTPnW+OcQ/PR4b5vFtBHbzGA5qPTX+zdu7hHrdWb+SzS9XA+up8BNB+9u3txt3WQaCDHoheouay8vx7OR08wgOaj3Q/hGDs3Ri0d56VVA+ejLzGA5qPfSBbfLFJLx/rYzOv46+F89IX5+Qvz0fNV5rXYx7yjxlmP5qPtD8laPLVILR3nJVkP56PDPXMrnI++ygCcjw73FL1wPjp6nuHVs1ep+Z956Fvjr4fz0fX0gy3NB2DqvbmunqcezUeHe/5pQB/d09NT76lTSz6iVs/953k0H93LAJyPDvfs6nA++jQDcD56nAE0Hx1ue4mAPjrc/hLhfPTAwL4BerXfl97mReQFak6tM9dn18P56L8ZQPPR/j19zg+cp1Z+T6CoHs5Hh9saKJyP/oUBOB99YHPzwGZyEzZKSFR+s7lm07E2sx7NR/8VI3ZUFDsr6pg525rsejgffZABNB+9sPBg4QG1BSf6vG1tdj2cjz7Y2lrV3F7VtfWqivWtVr31aD66tTGuvnGujrmJrg1/PZyP/pkBNB+d3uo677bYAn29ux7OR+9nAM1Hf8kAnI8eio7F0P6hBJSQOdXrOXM+sx7NR7948ejFIwkFcexDX+eKk8D56K40Q11D1NzjLFL1aD66re1J2xNqbRIV671Cz9vWuuvhfHRfV1dfVx+16KCo2MwJunKuTeXQfHQbA3A+OjqGfaN9oxIKZKx6V07l+/LUo/noZzGvn72WUCBjW2+u03HXw/noY8UZPTZKrUABmo8+wwCcjzaOyZ/0n4P+SMWuNcfy1KP56N8YgPPRnzGA5qPfv7/3/l4mtChe54rdwPnoQwyg+eiPH29/vE2t1QtELFB5M1bode56OB9NL+2H6B/7sNYrbHk9Jzicpx7NR//IAJyPPswAmo++G/Pu7jsJBTIWvT5n5m1r7PVwPvooA2g++icG4Hx0wAMdzEe/lLx9+ZZaurfN6TmFvx7ORx9pcZT+3emPBGbOtiazHs1Hf/hw7cO1GBrIsep19JyIFdn1cD76CANoPvoHBuB89K8MoPnoqakrU1diaCDHoheouay8vx7OR3/OAJqPvpOLqTtT1O6UBM5H/84Amo8O93cO6KNZqH5y6J9cUVFRUVFRUVFRUVFRUVFRUVFRUfG/419pkqhrTJi5bQAAAABJRU5ErkJggg==)

Declaring colors & creating effects
-----------------------------------

All CSS gradient types are a range of position-dependent colors. The
colors produced by CSS gradients can vary continuously with position,
producing smooth color transitions. It is also possible to create bands
of solid colors, and hard transitions between two colors. The following
are valid for all gradient functions:

### Using more than two colors

You don\'t have to limit yourself to two colors---you may use as many as
you like! By default, colors are evenly spaced along the gradient.

[css]

```css
.auto-spaced-linear-gradient {
  background: linear-gradient(red, yellow, blue, orange);
}
```

### Positioning color stops

You don\'t have to leave your color stops at their default positions. To
fine-tune their locations, you can give each one zero, one, or two
percentage or, for radial and linear gradients, absolute length values.
If you specify the location as a percentage, `0%` represents the
starting point, while `100%` represents the ending point; however, you
can use values outside that range if necessary to get the effect you
want. If you leave a location unspecified, the position of that
particular color stop will be automatically calculated for you, with the
first color stop being at `0%` and the last color stop being at `100%`,
and any other color stops being half way between their adjacent color
stops.

[css]

```css
.multicolor-linear {
  background: linear-gradient(to left, lime 28px, red 77%, cyan);
}
```

### Creating hard lines

To create a hard line between two colors, creating a stripe instead of a
gradual transition, adjacent color stops can be set to the same
location. In this example, the colors share a color stop at the `50%`
mark, halfway through the gradient:

[css]

```css
.striped {
  background: linear-gradient(to bottom left, cyan 50%, palegoldenrod 50%);
}
```

### Gradient hints

By default, the gradient transitions evenly from one color to the next.
You can include a color-hint to move the midpoint of the transition
value to a certain point along the gradient. In this example, we\'ve
moved the midpoint of the transition from the 50% mark to the 10% mark.

[css]

```css
.color-hint {
  background: linear-gradient(blue, 10%, pink);
}
.simple-linear {
  background: linear-gradient(blue, pink);
}
```

### Creating color bands & stripes

To include a solid, non-transitioning color area within a gradient,
include two positions for the color stop. Color stops can have two
positions, which is equivalent to two consecutive color stops with the
same color at different positions. The color will reach full saturation
at the first color stop, maintain that saturation through to the second
color stop, and transition to the adjacent color stop\'s color through
the adjacent color stop\'s first position.

[css]

```css
.multiposition-stops {
  background: linear-gradient(
    to left,
    lime 20%,
    red 30%,
    red 45%,
    cyan 55%,
    cyan 70%,
    yellow 80%
  );
  background: linear-gradient(
    to left,
    lime 20%,
    red 30% 45%,
    cyan 55% 70%,
    yellow 80%
  );
}
.multiposition-stop2 {
  background: linear-gradient(
    to left,
    lime 25%,
    red 25%,
    red 50%,
    cyan 50%,
    cyan 75%,
    yellow 75%
  );
  background: linear-gradient(
    to left,
    lime 25%,
    red 25% 50%,
    cyan 50% 75%,
    yellow 75%
  );
}
```

In the first example above, the lime goes from the 0% mark, which is
implied, to the 20% mark, transitions from lime to red over the next 10%
of the width of the gradient, reach solid red at the 30% mark, and
staying solid red up until 45% through the gradient, where it fades to
cyan, being fully cyan for 15% of the gradient, and so on.

In the second example, the second color stop for each color is at the
same location as the first color stop for the adjacent color, creating a
striped effect.

In both examples, the gradient is written twice: the first is the CSS
Images Level 3 method of repeating the color for each stop and the
second example is the CSS Images Level 4 multiple color stop method of
including two color-stop-lengths in a linear-color-stop declaration.

### Controlling the progression of a gradient

By default, a gradient evenly progresses between the colors of two
adjacent color stops, with the midpoint between those two color stops
being the midpoint color value. You can control the
[interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation),
or progression, between two color stops by including a color hint
location. In this example, the color reaches the midpoint between lime
and cyan 20% of the way through the gradient rather than 50% of the way
through. The second example does not contain the hint to highlight the
difference the color hint can make:

[css]

```css
.colorhint-gradient {
  background: linear-gradient(to top, lime, 20%, cyan);
}
.regular-progression {
  background: linear-gradient(to top, lime, cyan);
}
```

### Overlaying gradients

Gradients support transparency, so you can stack multiple backgrounds to
achieve some pretty fancy effects. The backgrounds are stacked from top
to bottom, with the first specified being on top.

[css]

```css
.layered-image {
  background: linear-gradient(to right, transparent, mistyrose),
    url("critters.png");
}
```

### Stacked gradients

You can even stack gradients with other gradients. As long as the top
gradients aren\'t entirely opaque, the gradients below will still be
visible.

[css]

```css
.stacked-linear {
  background: linear-gradient(
      217deg,
      rgba(255, 0, 0, 0.8),
      rgba(255, 0, 0, 0) 70.71%
    ), linear-gradient(127deg, rgba(0, 255, 0, 0.8), rgba(0, 255, 0, 0) 70.71%),
    linear-gradient(336deg, rgba(0, 0, 255, 0.8), rgba(0, 0, 255, 0) 70.71%);
}
```

Using radial gradients
----------------------

Radial gradients are similar to linear gradients, except that they
radiate out from a central point. You can dictate where that central
point is. You can also make them circular or elliptical.

### A basic radial gradient

As with linear gradients, all you need to create a radial gradient are
two colors. By default, the center of the gradient is at the 50% 50%
mark, and the gradient is elliptical matching the aspect ratio of its
box:

[css]

```css
.simple-radial {
  background: radial-gradient(red, blue);
}
```

### Positioning radial color stops

Again like linear gradients, you can position each radial color stop
with a percentage or absolute length.

[css]

```css
.radial-gradient {
  background: radial-gradient(red 10px, yellow 30%, #1e90ff 50%);
}
```

### Positioning the center of the gradient

You can position the center of the gradient with keyterms, percentage,
or absolute lengths, length and percentage values repeating if only one
is present, otherwise in the order of position from the left and
position from the top.

[css]

```css
.radial-gradient {
  background: radial-gradient(at 0% 30%, red 10px, yellow 30%, #1e90ff 50%);
}
```

### Sizing radial gradients

Unlike linear gradients, you can specify the size of radial gradients.
Possible values include `closest-corner`, `closest-side`,
`farthest-corner`, and `farthest-side`, with `farthest-corner` being the
default. Circles can also be sized with a length, and ellipses a length
or percentage.

#### Example: `closest-side` for ellipses

This example uses the `closest-side` size value, which means the size is
set by the distance from the starting point (the center) to the closest
side of the enclosing box.

[css]

```css
.radial-ellipse-side {
  background: radial-gradient(
    ellipse closest-side,
    red,
    yellow 10%,
    #1e90ff 50%,
    beige
  );
}
```

#### Example: `farthest-corner` for ellipses

This example is similar to the previous one, except that its size is
specified as `farthest-corner`, which sets the size of the gradient by
the distance from the starting point to the farthest corner of the
enclosing box from the starting point.

[css]

```css
.radial-ellipse-far {
  background: radial-gradient(
    ellipse farthest-corner at 90% 90%,
    red,
    yellow 10%,
    #1e90ff 50%,
    beige
  );
}
```

#### Example: `closest-side` for circles

This example uses `closest-side`, which makes the circle\'s radius to be
the distance between the center of the gradient and the closest side. In
this case the radius is the distance between the center and the bottom
edge, because the gradient is placed 25% from the left and 25% from the
bottom, and the div element\'s height is smaller than the width.

[css]

```css
.radial-circle-close {
  background: radial-gradient(
    circle closest-side at 25% 75%,
    red,
    yellow 10%,
    #1e90ff 50%,
    beige
  );
}
```

#### Example: length or percentage for ellipses

For ellipses only, you can size the ellipse using a length or
percentage. The first value represents the horizontal radius, the second
the vertical radius, where you use a percentage this corresponds to the
size of the box in that dimension. In the below example I have used a
percentage for the horizontal radius.

[css]

```css
.radial-ellipse-size {
  background: radial-gradient(
    ellipse 50% 50px,
    red,
    yellow 10%,
    #1e90ff 50%,
    beige
  );
}
```

#### Example: length for circles

For circles the size may be given as a [\<length\>](length.md), which is
the size of the circle.

[css]

```css
.radial-circle-size {
  background: radial-gradient(circle 50px, red, yellow 10%, #1e90ff 50%, beige);
}
```

### Stacked radial gradients

Just like linear gradients, you can also stack radial gradients. The
first specified is on top, the last on the bottom.

[css]

```css
.stacked-radial {
  background:
    radial-gradient(
      circle at 50% 0,
      rgba(255, 0, 0, 0.5),
      rgba(255, 0, 0, 0) 70.71%
    ),
    radial-gradient(
      circle at 6.7% 75%,
      rgba(0, 0, 255, 0.5),
      rgba(0, 0, 255, 0) 70.71%
    ),
    radial-gradient(
        circle at 93.3% 75%,
        rgba(0, 255, 0, 0.5),
        rgba(0, 255, 0, 0) 70.71%
      ) beige;
  border-radius: 50%;
}
```

Using conic gradients
---------------------

The `conic-gradient()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) function creates
an image consisting of a gradient with color transitions rotated around
a center point (rather than radiating from the center). Example conic
gradients include pie charts and [color
wheels](https://developer.mozilla.org/en-US/docs/Glossary/Color_wheel),
but they can also be used for creating checker boards and other
interesting effects.

The conic-gradient syntax is similar to the radial-gradient syntax, but
the color-stops are placed around a gradient arc, the circumference of a
circle, rather than on the gradient line emerging from the center of the
gradient, and the color-stops are percentages or degrees: absolute
lengths are not valid.

In a radial gradient, the colors transition from the center of an
ellipse, outward, in all directions. With conic gradients, the colors
transition as if spun around the center of a circle, starting at the top
and going clockwise. Similar to radial gradients, you can position the
center of the gradient. Similar to linear gradients, you can change the
gradient angle.

### A basic conic gradient

As with linear and radial gradients, all you need to create a conic
gradient are two colors. By default, the center of the gradient is at
the 50% 50% mark, with the start of the gradient facing up:

[css]

```css
.simple-conic {
  background: conic-gradient(red, blue);
}
```

### Positioning the conic center

Like radial gradients, you can position the center of the conic gradient
with keyterms, percentage, or absolute lengths, with the keyword \"at\"

[css]

```css
.conic-gradient {
  background: conic-gradient(at 0% 30%, red 10%, yellow 30%, #1e90ff 50%);
}
```

### Changing the angle

By default, the different color stops you specify are spaced
equidistantly around the circle. You can position the starting angle of
the conic gradient using the \"from\" keyword at the beginning followed
by an angle or a length, and you can specify different positions for the
colors stops by including an angle or length after them.

[css]

```css
.conic-gradient {
  background: conic-gradient(from 45deg, red, orange 50%, yellow 85%, green);
}
```

Using repeating gradients
-------------------------

The [`linear-gradient()`](linear-gradient.md),
[`radial-gradient()`](radial-gradient.md), and
[`conic-gradient()`](conic-gradient.md) functions don\'t
support automatically repeated color stops. However, the
[`repeating-linear-gradient()`](repeating-linear-gradient.md),
[`repeating-radial-gradient()`](repeating-radial-gradient.md),
and [`repeating-conic-gradient()`](repeating-conic-gradient.md)
functions are available to offer this functionality.

The size of the gradient line or arc that repeats is the length between
the first color stop value and the last color stop length value. If the
first color stop just has a color and no color stop length, the value
defaults to 0. If the last color stop has just a color and no color stop
length, the value defaults to 100%. If neither is declared, the gradient
line is 100% meaning the linear and conic gradients will not repeat and
the radial gradient will only repeat if the radius of the gradient is
smaller than the length between the center of the gradient and the
farthest corner. If the first color stop is declared, and the value is
greater than 0, the gradient will repeat, as the size of the line or arc
is the difference between the first color stop and last color stop is
less than 100% or 360 degrees.

### Repeating linear gradients

This example uses
[`repeating-linear-gradient()`](repeating-linear-gradient.md)
to create a gradient that progresses repeatedly in a straight line. The
colors get cycled over again as the gradient repeats. In this case the
gradient line is 10px long.

[css]

```css
.repeating-linear {
  background: repeating-linear-gradient(
    -45deg,
    red,
    red 5px,
    blue 5px,
    blue 10px
  );
}
```

### Multiple repeating linear gradients

Similar to regular linear and radial gradients, you can include multiple
gradients, one on top of the other. This only makes sense if the
gradients are partially transparent allowing subsequent gradients to
show through the transparent areas, or if you include different
[background-sizes](background-size.md), optionally with different
[background-position](background-position.md) property values, for each
gradient image. We are using transparency.

In this case the gradient lines are 300px, 230px, and 300px long.

[css]

```css
.multi-repeating-linear {
  background: repeating-linear-gradient(
      190deg,
      rgba(255, 0, 0, 0.5) 40px,
      rgba(255, 153, 0, 0.5) 80px,
      rgba(255, 255, 0, 0.5) 120px,
      rgba(0, 255, 0, 0.5) 160px,
      rgba(0, 0, 255, 0.5) 200px,
      rgba(75, 0, 130, 0.5) 240px,
      rgba(238, 130, 238, 0.5) 280px,
      rgba(255, 0, 0, 0.5) 300px
    ), repeating-linear-gradient(
      -190deg,
      rgba(255, 0, 0, 0.5) 30px,
      rgba(255, 153, 0, 0.5) 60px,
      rgba(255, 255, 0, 0.5) 90px,
      rgba(0, 255, 0, 0.5) 120px,
      rgba(0, 0, 255, 0.5) 150px,
      rgba(75, 0, 130, 0.5) 180px,
      rgba(238, 130, 238, 0.5) 210px,
      rgba(255, 0, 0, 0.5) 230px
    ), repeating-linear-gradient(23deg, red 50px, orange 100px, yellow 150px, green
        200px, blue 250px, indigo 300px, violet 350px, red 370px);
}
```

### Plaid gradient

To create plaid we include several overlapping gradients with
transparency. In the first background declaration we listed every color
stop separately. The second background property declaration using the
multiple position color stop syntax:

[css]

```css
.plaid-gradient {
  background: repeating-linear-gradient(
      90deg,
      transparent,
      transparent 50px,
      rgba(255, 127, 0, 0.25) 50px,
      rgba(255, 127, 0, 0.25) 56px,
      transparent 56px,
      transparent 63px,
      rgba(255, 127, 0, 0.25) 63px,
      rgba(255, 127, 0, 0.25) 69px,
      transparent 69px,
      transparent 116px,
      rgba(255, 206, 0, 0.25) 116px,
      rgba(255, 206, 0, 0.25) 166px
    ), repeating-linear-gradient(
      0deg,
      transparent,
      transparent 50px,
      rgba(255, 127, 0, 0.25) 50px,
      rgba(255, 127, 0, 0.25) 56px,
      transparent 56px,
      transparent 63px,
      rgba(255, 127, 0, 0.25) 63px,
      rgba(255, 127, 0, 0.25) 69px,
      transparent 69px,
      transparent 116px,
      rgba(255, 206, 0, 0.25) 116px,
      rgba(255, 206, 0, 0.25) 166px
    ), repeating-linear-gradient(
      -45deg,
      transparent,
      transparent 5px,
      rgba(143, 77, 63, 0.25) 5px,
      rgba(143, 77, 63, 0.25) 10px
    ), repeating-linear-gradient(45deg, transparent, transparent 5px, rgba(
          143,
          77,
          63,
          0.25
        ) 5px, rgba(143, 77, 63, 0.25) 10px);

  background: repeating-linear-gradient(
      90deg,
      transparent 0 50px,
      rgba(255, 127, 0, 0.25) 50px 56px,
      transparent 56px 63px,
      rgba(255, 127, 0, 0.25) 63px 69px,
      transparent 69px 116px,
      rgba(255, 206, 0, 0.25) 116px 166px
    ), repeating-linear-gradient(
      0deg,
      transparent 0 50px,
      rgba(255, 127, 0, 0.25) 50px 56px,
      transparent 56px 63px,
      rgba(255, 127, 0, 0.25) 63px 69px,
      transparent 69px 116px,
      rgba(255, 206, 0, 0.25) 116px 166px
    ), repeating-linear-gradient(
      -45deg,
      transparent 0 5px,
      rgba(143, 77, 63, 0.25) 5px 10px
    ), repeating-linear-gradient(45deg, transparent 0 5px, rgba(
          143,
          77,
          63,
          0.25
        ) 5px 10px);
}
```

### Repeating radial gradients

This example uses
[`repeating-radial-gradient()`](repeating-radial-gradient.md)
to create a gradient that radiates repeatedly from a central point. The
colors get cycled over and over as the gradient repeats.

[css]

```css
.repeating-radial {
  background: repeating-radial-gradient(
    black,
    black 5px,
    white 5px,
    white 10px
  );
}
```

### Multiple repeating radial gradients

[css]

```css
.multi-target {
  background:
    repeating-radial-gradient(
        ellipse at 80% 50%,
        rgba(0, 0, 0, 0.5),
        rgba(0, 0, 0, 0.5) 15px,
        rgba(255, 255, 255, 0.5) 15px,
        rgba(255, 255, 255, 0.5) 30px
      ) top left no-repeat,
    repeating-radial-gradient(
        ellipse at 20% 50%,
        rgba(0, 0, 0, 0.5),
        rgba(0, 0, 0, 0.5) 10px,
        rgba(255, 255, 255, 0.5) 10px,
        rgba(255, 255, 255, 0.5) 20px
      ) top left no-repeat yellow;
  background-size:
    200px 200px,
    150px 150px;
}
```

See also
--------

- Gradient functions:
    [`linear-gradient()`](linear-gradient.md),
    [`radial-gradient()`](radial-gradient.md),
    [`conic-gradient()`](conic-gradient.md),
    [`repeating-linear-gradient()`](repeating-linear-gradient.md),
    [`repeating-radial-gradient()`](repeating-radial-gradient.md),
    [`repeating-conic-gradient()`](repeating-conic-gradient.md)
- Gradient-related CSS data types: [`<gradient>`](gradient.md),
    [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- Gradient-related CSS properties: [`background`](background.md),
    [`background-image`](background-image.md)
- [CSS Gradients Patterns Gallery, by Lea
    Verou](https://projects.verou.me/css3patterns/)
- [CSS Gradients Library, by Estelle
    Weyl](https://standardista.com/cssgradients/)
- [Gradient CSS
    Generator](https://cssgenerator.org/gradient-css-generator.html)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images/Using_CSS_gradients>
