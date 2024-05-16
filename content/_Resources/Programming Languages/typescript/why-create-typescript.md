What is JavaScript?
===================

 
TypeScript is a language from Microsoft which builds on JavaScript.\
This post is a non-technical overview of what JavaScript is, how
TypeScript extends JavaScript and what problems it solves.


 
What is JavaScript?
-------------------

Because TypeScript extends JavaScript, this makes it a good starting
point. JavaScript is commonly used to create websites. When building a
website, you work with three languages: HTML, CSS and JavaScript (JS).
Broadly speaking: HTML defines the content which will appear on the
page, CSS defines the visual style of the page, and JS defines the
interactive behaviors of the page.

We describe having these sets of skills as being a \"front-end\"
developer. You use three languages to create pages inside a web browser
like Safari, Firefox, Edge or Chrome. Given how popular the web is for
commerce and information sharing, there is a massive demand for people
who are good at using these three languages.

Related to the role of being a \"front-end\" developer is the set of
skills for the \"back-end\" developers, which are to create computer
services that communicate either to a web browser (by passing it
HTML/CSS/JS) or to another service (by sending data more directly.) You
don\'t need to use HTML, CSS or JS to write this type of code, but it\'s
usually an end-product of your work because it is likely to be presented
in a web browser.

### What do Programming Languages do?

Programming languages are a way for humans and computers to communicate.
People read code many, many multiples of times more than they write it -
so developers create programming languages which are good at solving
particular problems with a small amount of code. Here\'s an example
using JavaScript:

```typescript
var name = "Danger"
console.log("Hello, " + name)
```

The first line makes a variable (effectively a box you can store other
things in) and then the second line outputs text to the console (for
example DOS, or the terminal) `"Hello, Danger"`.

JavaScript is designed to work as a scripting language, which means the
code starts at the top of the file and then goes through line by line
downwards running that code. To provide some contrast, here is the same
behavior in Java, which is built with different language constraints:

```typescript
class Main {
  public static void main(String[] args) {
    String name = "Danger";
    System.out.println("Hello, " + name);
  }
}
```

These two code samples do the same thing, however the Java version comes
with a lot of words that aren\'t necessarily about telling the computer
exactly what to do, e.g. `class Main {`,
`public static void main(String[] args) {`, and two extra `}`s. It also
has semi-colons at the end of some lines. Neither of these programming
languages are wrong, Java however, is aimed at building different things
from JavaScript, and these extra bits of code make sense within the
constraints of building a Java app.

To get to the key point though, there is one standout line I\'d like us
to compare:

```typescript
// JavaScript
var name = "Danger"

// Java
String name = "Danger";
```

Both of these lines declare variables called `name` which contain the
value `"Danger"`.

In JavaScript you use the abbreviation `var` to declare a variable.
Meanwhile, in Java you need to say *what kind of data* the variable
contains. In this case the variable contains a `String`. (A string is a
programming term for a collection of characters. They
`"look like this"`. This [5m
video](https://www.youtube.com/watch?v=czTWbdwbt7E) is a good primer if
you want to learn more.)

Both of these variables contain a string, but the difference is that in
Java the variable can *only* ever contain a *string*, because that\'s
what we said when we created the variable. In JS, the variable can
change to be *anything*, like a number, or a list of dates.

To illustrate:

```typescript
// Before in JS
var name = "Danger"
// Also OK
var name = 1
var name = false
var name = ["2018-02-03", "2019-01-12"]

// Before in Java
String name = "Danger";
// Not OK, the code wouldn't be accepted by Java
String name = 1;
String name = false
String name = new String[]{"2018-02-03", "2019-01-12"};
```

These trade-offs make sense in the context for which these languages
were built back in 1995. JavaScript was originally designed to be a
small programming language which handled simple interactions on
websites. Java on the other hand was built specifically to make complex
apps which could run on any computer. They expected to be used to build
codebases of different scales, so the language required programmers
write different types of code.

Java required programmers to be more explicit with the values of their
variables because the programs they expected people to build were more
complex. While JavaScript opted for ease of reading by omitting
information about the specifics, and expected codebases to be
significantly smaller.

### What is TypeScript?

TypeScript is a programming language - it contains all of JavaScript,
and then a bit more. Using our example above, let\'s compare the scripts
for \"Hello, Danger\" in JavaScript vs TypeScript:

```typescript
// JavaScript
var name = "Danger"
console.log("Hello, " + name)

// TypeScript
var name = "Danger"
console.log("Hello, " + name)

// Yep, you're not missing something, there's no difference
```

Due to TypeScript\'s goal of only *extending* JavaScript, the existing
JavaScript code we saw works as TypeScript. The extensions which
TypeScript adds to JavaScript are intended to help you be more explicit
about what kinds of data are used in your code, a bit like Java.

Here is the same sample, but using TypeScript to be more explicit about
what the variable is:

```typescript
var name: string = "Danger"
console.log("Hello, " + name)
```

This extra `: string` allow the reader to be certain that `name` will
only be a string. Annotating your variables in this way also gives
TypeScript the chance to verify that these match. This is *very* useful,
because keeping track of changes like the type of value in a variable
seems easy when it\'s one or two, but once it starts hitting the
hundreds, that\'s a lot to keep track of. Writing types help programmers
be more confident about their code because types catch mistakes.

Simply speaking, we call these annotations \"Types\". Hence the name
*Type*Script. One of the tag-lines for TypeScript is \"JavaScript which
scales\" which is a statement that these extra type annotations allows
you to work on bigger projects. This is because you can verify up-front
how correct your code is. This means you have less need to understand
how every change affects the rest of the program.

In the 90s, and maybe until a 5-10 years ago the trade-off for not
having types in your JavaScript application was fine because the size
and complexities of the programs being built were constrained to just
the front-end of websites. Today though, JavaScript is being used almost
everywhere, to build almost anything which runs on a computer. A large
amount of mobile and desktop apps use JavaScript and web technology
under the hood.

These are all considerably more complicated to build and understand,
adding types drastically reduces the complexity of making improvements
to those programs.

### What Problems Can TypeScript Solve?

Typically, the need to ensure there are no bugs in your code can be
handled by writing automated tests, then by manually verifying that the
code works as you expect and finally having another person validate that
it seems correct.

Not many companies are the size of Microsoft, however a lot of all
problems writing JavaScript in large codebases are the same. Many
JavaScript apps are made up of hundreds of thousands of files. A single
change to one individual file can affect the behaviour of any number of
other files, like throwing a pebble into a pond and causing ripples to
spread out to the bank.

Validating the connections between every part of your project can get
time consuming quickly, using a type-checked language like TypeScript
can handle that automatically and provide instant feedback during
development.

These features allows TypeScript to help developers feel more confident
in their code, and save considerable amounts time in validating that
they have not accidentally broken the project.


 
© 2012-2023 Microsoft\
Licensed under the Apache License, Version 2.0.\
https://www.typescriptlang.org/why-create-typescript>

