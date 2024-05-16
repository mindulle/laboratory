Operator precedence
===================

 
**Operator precedence** determines how operators are parsed concerning
each other. Operators with higher precedence become the operands of
operators with lower precedence.


 
Try it 
------

 



 
Precedence and associativity 
----------------------------

 
Consider an expression describable by the representation below, where
both `OP1` and `OP2` are fill-in-the-blanks for OPerators.

```text
a OP1 b OP2 c
```

The combination above has two possible interpretations:

```text
(a OP1 b) OP2 c
a OP1 (b OP2 c)
```

Which one the language decides to adopt depends on the identity of `OP1`
and `OP2`.

If `OP1` and `OP2` have different precedence levels (see the table
below), the operator with the higher *precedence* goes first and
associativity does not matter. Observe how multiplication has higher
precedence than addition and executed first, even though addition is
written first in the code.

 
 
[js]


```js
console.log(3 + 10 * 2); // 23
console.log(3 + (10 * 2)); // 23, because parentheses here are superfluous
console.log((3 + 10) * 2); // 26, because the parentheses change the order
```


Within operators of the same precedence, the language groups them by
*associativity*. *Left-associativity* (left-to-right) means that it is
interpreted as `(a OP1 b) OP2 c`, while *right-associativity*
(right-to-left) means it is interpreted as `a OP1 (b OP2 c)`. Assignment
operators are right-associative, so you can write:

 
 
[js]


```js
a = b = 5; // same as writing a = (b = 5);
```


with the expected result that `a` and `b` get the value 5. This is
because the assignment operator returns the value that is assigned.
First, `b` is set to 5. Then the `a` is also set to 5 --- the return
value of `b = 5`, a.k.a. right operand of the assignment.

As another example, the unique exponentiation operator has
right-associativity, whereas other arithmetic operators have
left-associativity.

 
 
[js]


```js
const a = 4 ** 3 ** 2; // Same as 4 ** (3 ** 2); evaluates to 262144
const b = 4 / 3 / 2; // Same as (4 / 3) / 2; evaluates to 0.6666...
```


Operators are first grouped by precedence, and then, for adjacent
operators that have the same precedence, by associativity. So, when
mixing division and exponentiation, the exponentiation always comes
before the division. For example, `2 ** 3 / 3 ** 2` results in
0.8888888888888888 because it is the same as `(2 ** 3) / (3 ** 2)`.

For prefix unary operators, suppose we have the following pattern:

```text
OP1 a OP2 b
```

where `OP1` is a prefix unary operator and `OP2` is a binary operator.
If `OP1` has higher precedence than `OP2`, then it would be grouped as
`(OP1 a) OP2 b`; otherwise, it would be `OP1 (a OP2 b)`.

 
 
[js]


```js
const a = 1;
const b = 2;
typeof a + b; // Equivalent to (typeof a) + b; result is "number2"
```


If the unary operator is on the second operand:

```text
a OP2 OP1 b
```

Then the binary operator `OP2` must have lower precedence than the unary
operator `OP1` for it to be grouped as `a OP2 (OP1 b)`. For example, the
following is invalid:

 
 
[js]


```js
function* foo() {
  a + yield 1;
}
```


Because `+` has higher precedence than [`yield`](yield), this would
become `(a + yield) 1` --- but because `yield` is a [reserved
word](../lexical_grammar#keywords) in generator functions, this would be
a syntax error. Luckily, most unary operators have higher precedence
than binary operators and do not suffer from this pitfall.

If we have two prefix unary operators:

```text
OP1 OP2 a
```

Then the unary operator closer to the operand, `OP2`, must have higher
precedence than `OP1` for it to be grouped as `OP1 (OP2 a)`. It\'s
possible to get it the other way and end up with `(OP1 OP2) a`:

 
 
[js]


```js
async function* foo() {
  await yield 1;
}
```


Because [`await`](await) has higher precedence than [`yield`](yield),
this would become `(await yield) 1`, which is awaiting an identifier
called `yield`, and a syntax error. Similarly, if you have `new !A;`,
because `!` has lower precedence than `new`, this would become
`(new !) A`, which is obviously invalid. (This code looks nonsensical to
write anyway, since `!A` always produces a boolean, not a constructor
function.)

For postfix unary operators (namely, `++` and `--`), the same rules
apply. Luckily, both operators have higher precedence than any binary
operator, so the grouping is always what you would expect. Moreover,
because `++` evaluates to a *value*, not a *reference*, you can\'t chain
multiple increments together either, as you may do in C.

 
 
[js]


```js
let a = 1;
a++++; // SyntaxError: Invalid left-hand side in postfix operation.
```


Operator precedence will be handled *recursively*. For example, consider
this expression:

 
 
[js]


```js
1 + 2 ** 3 * 4 / 5 >> 6
```


First, we group operators with different precedence by decreasing levels
of precedence.

1.  The `**` operator has the highest precedence, so it\'s grouped
    first.
2.  Looking around the `**` expression, it has `*` on the right and `+`
    on the left. `*` has higher precedence, so it\'s grouped first. `*`
    and `/` have the same precedence, so we group them together for now.
3.  Looking around the `*`/`/` expression grouped in 2, because `+` has
    higher precedence than `>>`, the former is grouped.

 
 
[js]


```js
   (1 + ( (2 ** 3) * 4 / 5) ) >> 6
// │    │ └─ 1. ─┘        │ │
// │    └────── 2. ───────┘ │
// └────────── 3. ──────────┘
```


Within the `*`/`/` group, because they are both left-associative, the
left operand would be grouped.

 
 
[js]


```js
   (1 + ( ( (2 ** 3) * 4 ) / 5) ) >> 6
// │    │ │ └─ 1. ─┘     │    │ │
// │    └─│─────── 2. ───│────┘ │
// └──────│───── 3. ─────│──────┘
//        └───── 4. ─────┘
```


Note that operator precedence and associativity only affect the order of
evaluation of *operators* (the implicit grouping), but not the order of
evaluation of *operands*. The operands are always evaluated from
left-to-right. The higher-precedence expressions are always evaluated
first, and their results are then composed according to the order of
operator precedence.

 
 
[js]


```js
function echo(name, num) {
  console.log(`Evaluating the ${name} side`);
  return num;
}
// Exponentiation operator (**) is right-associative,
// but all call expressions (echo()), which have higher precedence,
// will be evaluated before ** does
console.log(echo("left", 4) ** echo("middle", 3) ** echo("right", 2));
// Evaluating the left side
// Evaluating the middle side
// Evaluating the right side
// 262144

// Exponentiation operator (**) has higher precedence than division (/),
// but evaluation always starts with the left operand
console.log(echo("left", 4) / echo("middle", 3) ** echo("right", 2));
// Evaluating the left side
// Evaluating the middle side
// Evaluating the right side
// 0.4444444444444444
```


If you are familiar with binary trees, think about it as a [post-order
traversal](https://en.wikipedia.org/wiki/Tree_traversal#Post-order,_LRN).

```text
                /
       ┌────────┴────────┐
echo("left", 4)         **
                ┌────────┴────────┐
        echo("middle", 3)  echo("right", 2)
```

After all operators have been properly grouped, the binary operators
would form a binary tree. Evaluation starts from the outermost group ---
which is the operator with the lowest precedence (`/` in this case). The
left operand of this operator is first evaluated, which may be composed
of higher-precedence operators (such as a call expression
`echo("left", 4)`). After the left operand has been evaluated, the right
operand is evaluated in the same fashion. Therefore, all leaf nodes ---
the `echo()` calls --- would be visited left-to-right, regardless of the
precedence of operators joining them.



 
Short-circuiting
----------------

 
In the previous section, we said \"the higher-precedence expressions are
always evaluated first\" --- this is generally true, but it has to be
amended with the acknowledgement of *short-circuiting*, in which case an
operand may not be evaluated at all.

Short-circuiting is jargon for conditional evaluation. For example, in
the expression `a && (b + c)`, if `a` is
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy), then
the sub-expression `(b + c)` will not even get evaluated, even if it is
grouped and therefore has higher precedence than `&&`. We could say that
the logical AND operator (`&&`) is \"short-circuited\". Along with
logical AND, other short-circuited operators include logical OR (`||`),
nullish coalescing (`??`), and optional chaining (`?.`).

 
 
[js]


```js
a || (b * c); // evaluate `a` first, then produce `a` if `a` is "truthy"
a && (b < c); // evaluate `a` first, then produce `a` if `a` is "falsy"
a ?? (b || c); // evaluate `a` first, then produce `a` if `a` is not `null` and not `undefined`
a?.b.c; // evaluate `a` first, then produce `undefined` if `a` is `null` or `undefined`
```


When evaluating a short-circuited operator, the left operand is always
evaluated. The right operand will only be evaluated if the left operand
cannot determine the result of the operation.

 
**Note:** The behavior of short-circuiting is baked in these operators.
Other operators would *always* evaluate both operands, regardless if
that\'s actually useful --- for example, `NaN * foo()` will always call
`foo`, even when the result would never be something other than `NaN`.


The previous model of a post-order traversal still stands. However,
after the left subtree of a short-circuiting operator has been visited,
the language will decide if the right operand needs to be evaluated. If
not (for example, because the left operand of `||` is already truthy),
the result is directly returned without visiting the right subtree.

Consider this case:

 
 
[js]


```js
function A() { console.log('called A'); return false; }
function B() { console.log('called B'); return false; }
function C() { console.log('called C'); return true; }

console.log(C() || B() && A());

// Logs:
// called C
// true
```


Only `C()` is evaluated, despite `&&` having higher precedence. This
does not mean that `||` has higher precedence in this case --- it\'s
exactly *because* `(B() && A())` has higher precedence that causes it to
be neglected as a whole. If it\'s re-arranged as:

 
 
[js]


```js
console.log(A() && C() || B());
// Logs:
// called A
// called B
// false
```


Then the short-circuiting effect of `&&` would only prevent `C()` from
being evaluated, but because `A() && C()` as a whole is `false`, `B()`
would still be evaluated.

However, note that short-circuiting does not change the final evaluation
outcome. It only affects the evaluation of *operands*, not how
*operators* are grouped --- if evaluation of operands doesn\'t have side
effects (for example, logging to the console, assigning to variables,
throwing an error), short-circuiting would not be observable at all.

The assignment counterparts of these operators
([`&&=`](logical_and_assignment), [`||=`](logical_or_assignment),
[`??=`](nullish_coalescing_assignment)) are short-circuited as well.
They are short-circuited in a way that the assignment does not happen at
all.



 
Table
-----

 
The following table lists operators in order from highest precedence
(18) to lowest precedence (1).

Several general notes about the table:

1.  Not all syntax included here are \"operators\" in the strict sense.
    For example, spread `...` and arrow `=>` are typically not regarded
    as operators. However, we still included them to show how tightly
    they bind compared to other operators/expressions.
2.  Some operators have certain operands that require expressions
    narrower than those produced by higher-precedence operators. For
    example, the right-hand side of member access `.` (precedence 17)
    must be an identifier instead of a grouped expression. The left-hand
    side of arrow `=>` (precedence 2) must be an arguments list or a
    single identifier instead of some random expression.
3.  Some operators have certain operands that accept expressions wider
    than those produced by higher-precedence operators. For example, the
    bracket-enclosed expression of bracket notation `[ … ]`
    (precedence 17) can be any expression, even comma (precedence 1)
    joined ones. These operators act as if that operand is
    \"automatically grouped\". In this case we will omit the
    associativity.

 
Precedence




Associativity

Individual operators

Notes

18: grouping

n/a

[Grouping](grouping)\
`(x)`

\[1\]

17: access and call

left-to-right

[Member access](property_accessors#dot_notation)\
`x.y`

\[2\]

[Optional chaining](optional_chaining)\
`x?.y`

n/a

[Computed member access](property_accessors#bracket_notation)\
`x[y]`

\[3\]

[`new`](new) with argument list\
`new x(y)`

\[4\]

[Function
call](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)\
`x(y)`

[`import(x)`](import)

16: new

n/a

[`new`](new) without argument list\
`new x`

15: postfix operators

n/a

[Postfix increment](increment)\
`x++`

\[5\]

[Postfix decrement](decrement)\
`x--`

14: prefix operators

n/a

[Prefix increment](increment)\
`++x`

\[6\]

[Prefix decrement](decrement)\
`--x`

[Logical NOT](logical_not)\
`!x`

[Bitwise NOT](bitwise_not)\
`~x`

[Unary plus](unary_plus)\
`+x`

[Unary negation](unary_negation)\
`-x`

[`typeof x`](typeof)

[`void x`](void)

[`delete x`](delete)

\[7\]

[`await x`](await)

13: exponentiation

right-to-left

[Exponentiation](exponentiation)\
`x ** y`

\[8\]

12: multiplicative operators

left-to-right

[Multiplication](multiplication)\
`x * y`

[Division](division)\
`x / y`

[Remainder](remainder)\
`x % y`

11: additive operators

left-to-right

[Addition](addition)\
`x + y`

[Subtraction](subtraction)\
`x - y`

10: bitwise shift

left-to-right

[Left shift](left_shift)\
`x << y`

[Right shift](right_shift)\
`x >> y`

[Unsigned right shift](unsigned_right_shift)\
`x >>> y`

9: relational operators

left-to-right

[Less than](less_than)\
`x < y`

[Less than or equal](less_than_or_equal)\
`x <= y`

[Greater than](greater_than)\
`x > y`

[Greater than or equal](greater_than_or_equal)\
`x >= y`

[`x in y`](in)

[`x instanceof y`](instanceof)

8: equality operators

left-to-right

[Equality](equality)\
`x == y`

[Inequality](inequality)\
`x != y`

[Strict equality](strict_equality)\
`x === y`

[Strict inequality](strict_inequality)\
`x !== y`

7: bitwise AND

left-to-right

[Bitwise AND](bitwise_and)\
`x & y`

6: bitwise XOR

left-to-right

[Bitwise XOR](bitwise_xor)\
`x ^ y`

5: bitwise OR

left-to-right

[Bitwise OR](bitwise_or)\
`x | y`

4: logical AND

left-to-right

[Logical AND](logical_and)\
`x && y`

3: logical OR, nullish coalescing

left-to-right

[Logical OR](logical_or)\
`x || y`

[Nullish coalescing operator](nullish_coalescing)\
`x ?? y`

\[9\]

2: assignment and miscellaneous

right-to-left

[Assignment](assignment)\
`x = y`

\[10\]

[Addition assignment](addition_assignment)\
`x += y`

[Subtraction assignment](subtraction_assignment)\
`x -= y`

[Exponentiation assignment](exponentiation_assignment)\
`x **= y`

[Multiplication assignment](multiplication_assignment)\
`x *= y`

[Division assignment](division_assignment)\
`x /= y`

[Remainder assignment](remainder_assignment)\
`x %= y`

[Left shift assignment](left_shift_assignment)\
`x <<= y`

[Right shift assignment](right_shift_assignment)\
`x >>= y`

[Unsigned right shift assignment](unsigned_right_shift_assignment)\
`x >>>= y`

[Bitwise AND assignment](bitwise_and_assignment)\
`x &= y`

[Bitwise XOR assignment](bitwise_xor_assignment)\
`x ^= y`

[Bitwise OR assignment](bitwise_or_assignment)\
`x |= y`

[Logical AND assignment](logical_and_assignment)\
`x &&= y`

[Logical OR assignment](logical_or_assignment)\
`x ||= y`

[Nullish coalescing assignment](nullish_coalescing_assignment)\
`x ??= y`

right-to-left

[Conditional (ternary) operator](conditional_operator)\
`x ? y : z`

\[11\]

right-to-left

[Arrow](../functions/arrow_functions)\
`x => y`

\[12\]

n/a

[`yield x`](yield)

[`yield* x`](yield*)

[Spread](spread_syntax)\
`...x`

\[13\]

1: comma

left-to-right

[Comma operator](comma_operator)\
`x, y`

Notes:

1.  The operand can be any expression.
2.  The \"right-hand side\" must be an identifier.
3.  The \"right-hand side\" can be any expression.
4.  The \"right-hand side\" is a comma-separated list of any expression
    with precedence \> 1 (i.e. not comma expressions).
5.  The operand must be a valid assignment target (identifier or
    property access). Its precedence means `new Foo++` is `(new Foo)++`
    (a syntax error) and not `new (Foo++)` (a TypeError: (Foo++) is not
    a constructor).
6.  The operand must be a valid assignment target (identifier or
    property access).
7.  The operand cannot be an identifier or a [](privateProperties.md) access.
8.  The left-hand side cannot have precedence 14.
9.  The operands cannot be a logical OR `||` or logical AND `&&`
    operator without grouping.
10. The \"left-hand side\" must be a valid assignment target (identifier
    or property access).
11. The associativity means the two expressions after `?` are implicitly
    grouped.
12. The \"left-hand side\" is a single identifier or a parenthesized
    parameter list.
13. Only valid inside object literals, array literals, or argument
    lists.

 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence>

