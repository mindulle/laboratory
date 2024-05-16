Download TypeScript
===================

 
Download TypeScript
===================

TypeScript can be installed through three installation routes depending
on how you intend to use it: an npm module, a NuGet package or a Visual
Studio Extension.

If you are using Node.js, you want the npm version. If you are using
MSBuild in your project, you want the NuGet package or Visual Studio
extension.


 
TypeScript in Your Project
--------------------------

Having TypeScript set up on a per-project basis lets you have many
projects with many different versions of TypeScript, this keeps each
project working consistently.

 

### via npm

TypeScript is available as a [package on the npm
registry](https://www.npmjs.com/package/typescript) available as
`"typescript"`.

You will need a copy of
[Node.js](https://nodejs.org/en/ "Link to the node.js project") as an
environment to run the package. Then you use a dependency manager like
[npm](https://www.npmjs.com/ "Link to the npm package manager"),
[yarn](https://yarnpkg.com/ "Link to the yarn package manager") or
[pnpm](https://pnpm.js.org/ "Link to the pnpm package manager") to
download TypeScript into your project.

<div>

`npm install typescript --save-dev`\
\

npm

yarn

pnpm

</div>

All of these dependency managers support lockfiles, ensuring that
everyone on your team is using the same version of the language. You can
then run the TypeScript compiler using one of the following commands:

<div>

`npx tsc`\
\

npm

yarn

pnpm

</div>



### with Visual Studio

For most project types, you can get TypeScript as a package in Nuget for
your MSBuild projects, for example an ASP.NET Core app.

When using Nuget, you can [install TypeScript through Visual
Studio](https://learn.microsoft.com/visualstudio/javascript/tutorial-aspnet-with-typescript)
using:

-   The Manage NuGet Packages window (which you can get to by
    right-clicking on a project node)
-   The Nuget Package Manager Console (found in Tools \> NuGet Package
    Manager \> Package Manager Console) and then running:\
    `Install-Package Microsoft.TypeScript.MSBuild`{style="font-size:14px"}

For project types which don\'t support Nuget, you can use the
[TypeScript Visual Studio
extension](https://marketplace.visualstudio.com/items?itemName=TypeScriptTeam.typescript-53beta).
You can [install the
extension](https://learn.microsoft.com/visualstudio/ide/finding-and-using-visual-studio-extensions)
using `Extensions > Manage Extensions` in Visual Studio.




 
The examples below are for more advanced use cases.


 
Globally Installing TypeScript
------------------------------

It can be handy to have TypeScript available across all projects, often
to test one-off ideas. Long-term, codebases should prefer a project-wide
installation over a global install so that they can benefit from
reproducible builds across different machines.

 

### via npm

You can use npm to install TypeScript globally, this means that you can
use the `tsc` command anywhere in your terminal.

To do this, run `npm install -g typescript`. This will install the
latest version (currently 5.3).



### via Visual Studio Marketplace

You can install TypeScript as a Visual Studio extension, which will
allow you to use TypeScript across many MSBuild projects in Visual
Studio.

The latest version is available [in the Visual Studio
Marketplace](https://marketplace.visualstudio.com/items?itemName=TypeScriptTeam.typescript-53beta "Link to the Visual Studio Marketplace for the TypeScript MSBuild extension").




 
Working with TypeScript-compatible transpilers
----------------------------------------------

There are other tools which convert TypeScript files to JavaScript
files. You might use these tools for speed or consistency with your
existing build tooling.

Each of these projects handle the file conversion, but do not handle the
type-checking aspects of the TypeScript compiler. So it\'s likely that
you will still need to keep the above TypeScript dependency around, and
you will want to enable [`isolatedModules`](tsconfig#isolatedModules).

 

### Babel

[Babel](https://babeljs.io/) is a very popular JavaScript transpiler
which supports TypeScript files via the plugin
[\@babel/plugin-transform-typescript](https://babeljs.io/docs/en/babel-preset-typescript#docsNav).



### swc

[swc](https://swc-project.github.io/docs/installation/) is a fast
transpiler created in Rust which supports many of Babel\'s features
including TypeScript.



### Sucrase

[Sucrase](https://github.com/alangpierce/sucrase#sucrase/) is a Babel
fork focused on speed for using in development mode. Sucrase supports
TypeScript natively.




 
Next Steps 
----------

 
 
#### Get Started

-   [JS to TS](docs/handbook/typescript-in-5-minutes)
-   [New to Programming](docs/handbook/typescript-from-scratch)
-   [OOP to JS](docs/handbook/typescript-in-5-minutes-oop)
-   [Functional to JS](docs/handbook/typescript-in-5-minutes-func)
-   [Installation](download)


 
#### Handbook

-   [Everyday Types](docs/handbook/2/everyday-types)
-   [Creating Types from Types](docs/handbook/2/types-from-types)
-   [Object Types](docs/handbook/2/objects)
-   [Variable Declarations](docs/handbook/variable-declarations)
-   [More on Functions](docs/handbook/2/functions)


 
#### Tools

-   [Playground](https://www.typescriptlang.org/play/)
-   [TSConfig Reference](tsconfig/index)

#### Release Notes 

-   [What\'s new in
    5.3](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-3.html)


 
#### Tutorials

-   [ASP.NET](docs/handbook/asp-net-core)
-   [Migrating from JS](docs/handbook/migrating-from-javascript)
-   [Working with the DOM](docs/handbook/dom-manipulation)
-   [React & Webpack](docs/handbook/react-&-webpack)




 
© 2012-2023 Microsoft\
Licensed under the Apache License, Version 2.0.\
https://www.typescriptlang.org/download>

