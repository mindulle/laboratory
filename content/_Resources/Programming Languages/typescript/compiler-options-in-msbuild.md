Compiler Options in MSBuild
===========================

Overview 
--------

When you have an MSBuild based project which utilizes TypeScript such as
an ASP.NET Core project, you can configure TypeScript in two ways.
Either via a `tsconfig.json` or via the project settings.

Using a `tsconfig.json` 
-----------------------

We recommend using a `tsconfig.json` for your project when possible. To
add one to an existing project, add a new item to your project which is
called a "TypeScript JSON Configuration File" in modern versions of
Visual Studio.

The new `tsconfig.json` will then be used as the source of truth for
TypeScript-specific build information like files and configuration. You
can learn [about how TSConfigs works here](tsconfig-json) and there is a
[comprehensive reference here](https://www.typescriptlang.org/tsconfig).

Using Project Settings 
----------------------

You can also define the configuration for TypeScript inside you
project's settings. This is done by editing the XML in your `.csproj` to
define `PropertyGroups` which describe how the build can work:

```xml
<PropertyGroup>
  <TypeScriptNoEmitOnError>true</TypeScriptNoEmitOnError>
  <TypeScriptNoImplicitReturns>true</TypeScriptNoImplicitReturns>
</PropertyGroup>
```

There is a series of mappings for common TypeScript settings, these are
settings which map directly to [TypeScript cli
options](compiler-options) and are used to help you write a more
understandable project file. You can use the [TSConfig
reference](https://www.typescriptlang.org/tsconfig) to get more
information on what values and defaults are for each mapping.

### CLI Mappings

MSBuild Config Name

TSC Flag

`<TypeScriptAllowJS>`

`--allowJs`

Allow JavaScript files to be a part of your program. Use the `checkJS`
option to get errors from these files.

`<TypeScriptRemoveComments>`

`--removeComments`

Disable emitting comments.

`<TypeScriptNoImplicitAny>`

`--noImplicitAny`

Enable error reporting for expressions and declarations with an implied
`any` type..

`<TypeScriptGeneratesDeclarations>`

`--declaration`

Generate .d.ts files from TypeScript and JavaScript files in your
project.

`<TypeScriptModuleKind>`

`--module`

Specify what module code is generated.

`<TypeScriptJSXEmit>`

`--jsx`

Specify what JSX code is generated.

`<TypeScriptOutDir>`

`--outDir`

Specify an output folder for all emitted files.

`<TypeScriptSourceMap>`

`--sourcemap`

Create source map files for emitted JavaScript files.

`<TypeScriptTarget>`

`--target`

Set the JavaScript language version for emitted JavaScript and include
compatible library declarations.

`<TypeScriptNoResolve>`

`--noResolve`

Disallow `import`s, `require`s or `<reference>`s from expanding the
number of files TypeScript should add to a project.

`<TypeScriptMapRoot>`

`--mapRoot`

Specify the location where debugger should locate map files instead of
generated locations.

`<TypeScriptSourceRoot>`

`--sourceRoot`

Specify the root path for debuggers to find the reference source code.

`<TypeScriptCharset>`

`--charset`

No longer supported. In early versions, manually set the text encoding
for reading files.

`<TypeScriptEmitBOM>`

`--emitBOM`

Emit a UTF-8 Byte Order Mark (BOM) in the beginning of output files.

`<TypeScriptNoLib>`

`--noLib`

Disable including any library files, including the default lib.d.ts.

`<TypeScriptPreserveConstEnums>`

`--preserveConstEnums`

Disable erasing `const enum` declarations in generated code.

`<TypeScriptSuppressImplicitAnyIndexErrors>`

`--suppressImplicitAnyIndexErrors`

Suppress `noImplicitAny` errors when indexing objects that lack index
signatures.

`<TypeScriptNoEmitHelpers>`

`--noEmitHelpers`

Disable generating custom helper functions like `__extends` in compiled
output.

`<TypeScriptInlineSourceMap>`

`--inlineSourceMap`

Include sourcemap files inside the emitted JavaScript.

`<TypeScriptInlineSources>`

`--inlineSources`

Include source code in the sourcemaps inside the emitted JavaScript.

`<TypeScriptNewLine>`

`--newLine`

Set the newline character for emitting files.

`<TypeScriptIsolatedModules>`

`--isolatedModules`

Ensure that each file can be safely transpiled without relying on other
imports.

`<TypeScriptEmitDecoratorMetadata>`

`--emitDecoratorMetadata`

Emit design-type metadata for decorated declarations in source files.

`<TypeScriptRootDir>`

`--rootDir`

Specify the root folder within your source files.

`<TypeScriptExperimentalDecorators>`

`--experimentalDecorators`

Enable experimental support for TC39 stage 2 draft decorators.

`<TypeScriptModuleResolution>`

`--moduleResolution`

Specify how TypeScript looks up a file from a given module specifier.

`<TypeScriptSuppressExcessPropertyErrors>`

`--suppressExcessPropertyErrors`

Disable reporting of excess property errors during the creation of
object literals.

`<TypeScriptReactNamespace>`

`--reactNamespace`

Specify the object invoked for `createElement`. This only applies when
targeting `react` JSX emit.

`<TypeScriptSkipDefaultLibCheck>`

`--skipDefaultLibCheck`

Skip type checking .d.ts files that are included with TypeScript.

`<TypeScriptAllowUnusedLabels>`

`--allowUnusedLabels`

Disable error reporting for unused labels.

`<TypeScriptNoImplicitReturns>`

`--noImplicitReturns`

Enable error reporting for codepaths that do not explicitly return in a
function.

`<TypeScriptNoFallthroughCasesInSwitch>`

`--noFallthroughCasesInSwitch`

Enable error reporting for fallthrough cases in switch statements.

`<TypeScriptAllowUnreachableCode>`

`--allowUnreachableCode`

Disable error reporting for unreachable code.

`<TypeScriptForceConsistentCasingInFileNames>`

`--forceConsistentCasingInFileNames`

Ensure that casing is correct in imports.

`<TypeScriptAllowSyntheticDefaultImports>`

`--allowSyntheticDefaultImports`

Allow \'import x from y\' when a module doesn\'t have a default export.

`<TypeScriptNoImplicitUseStrict>`

`--noImplicitUseStrict`

Disable adding \'use strict\' directives in emitted JavaScript files.

`<TypeScriptLib>`

`--lib`

Specify a set of bundled library declaration files that describe the
target runtime environment.

`<TypeScriptBaseUrl>`

`--baseUrl`

Specify the base directory to resolve bare specifier module names.

`<TypeScriptDeclarationDir>`

`--declarationDir`

Specify the output directory for generated declaration files.

`<TypeScriptNoImplicitThis>`

`--noImplicitThis`

Enable error reporting when `this` is given the type `any`.

`<TypeScriptSkipLibCheck>`

`--skipLibCheck`

Skip type checking all .d.ts files.

`<TypeScriptStrictNullChecks>`

`--strictNullChecks`

When type checking, take into account `null` and `undefined`.

`<TypeScriptNoUnusedLocals>`

`--noUnusedLocals`

Enable error reporting when a local variables aren\'t read.

`<TypeScriptNoUnusedParameters>`

`--noUnusedParameters`

Raise an error when a function parameter isn\'t read

`<TypeScriptAlwaysStrict>`

`--alwaysStrict`

Ensure \'use strict\' is always emitted.

`<TypeScriptImportHelpers>`

`--importHelpers`

Allow importing helper functions from tslib once per project, instead of
including them per-file.

`<TypeScriptJSXFactory>`

`--jsxFactory`

Specify the JSX factory function used when targeting React JSX emit,
e.g. \'React.createElement\' or \'h\'

`<TypeScriptStripInternal>`

`--stripInternal`

Disable emitting declarations that have `@internal` in their JSDoc
comments.

`<TypeScriptCheckJs>`

`--checkJs`

Enable error reporting in type-checked JavaScript files.

`<TypeScriptDownlevelIteration>`

`--downlevelIteration`

Emit more compliant, but verbose and less performant JavaScript for
iteration.

`<TypeScriptStrict>`

`--strict`

Enable all strict type checking options.

`<TypeScriptNoStrictGenericChecks>`

`--noStrictGenericChecks`

Disable strict checking of generic signatures in function types.

`<TypeScriptPreserveSymlinks>`

`--preserveSymlinks`

Disable resolving symlinks to their realpath. This correlates to the
same flag in node.

`<TypeScriptStrictFunctionTypes>`

`--strictFunctionTypes`

When assigning functions, check to ensure parameters and the return
values are subtype-compatible.

`<TypeScriptStrictPropertyInitialization>`

`--strictPropertyInitialization`

Check for class properties that are declared but not set in the
constructor.

`<TypeScriptESModuleInterop>`

`--esModuleInterop`

Emit additional JavaScript to ease support for importing CommonJS
modules. This enables `allowSyntheticDefaultImports` for type
compatibility.

`<TypeScriptEmitDeclarationOnly>`

`--emitDeclarationOnly`

Only output d.ts files and not JavaScript files.

`<TypeScriptKeyofStringsOnly>`

`--keyofStringsOnly`

Make keyof only return strings instead of string, numbers or symbols.
Legacy option.

`<TypeScriptUseDefineForClassFields>`

`--useDefineForClassFields`

Emit ECMAScript-standard-compliant class fields.

`<TypeScriptDeclarationMap>`

`--declarationMap`

Create sourcemaps for d.ts files.

`<TypeScriptResolveJsonModule>`

`--resolveJsonModule`

Enable importing .json files

`<TypeScriptStrictBindCallApply>`

`--strictBindCallApply`

Check that the arguments for `bind`, `call`, and `apply` methods match
the original function.

`<TypeScriptNoEmitOnError>`

`--noEmitOnError`

Disable emitting files if any type checking errors are reported.

### Additional Flags 

Because the MSBuild system passes arguments directly to the TypeScript
CLI, you can use the option `TypeScriptAdditionalFlags` to provide
specific flags which don't have a mapping above.

For example, this would turn on
[`noPropertyAccessFromIndexSignature`](https://www.typescriptlang.org/tsconfig#noPropertyAccessFromIndexSignature):

```xml
<TypeScriptAdditionalFlags> $(TypeScriptAdditionalFlags) --noPropertyAccessFromIndexSignature</TypeScriptAdditionalFlags>
```

### Debug and Release Builds 

You can use PropertyGroup conditions to define different sets of
configurations. For example, a common task is stripping comments and
sourcemaps in production. In this example, we define a debug and release
property group which have different TypeScript configurations:

```xml
<PropertyGroup Condition="'$(Configuration)' == 'Debug'">
  <TypeScriptRemoveComments>false</TypeScriptRemoveComments>
  <TypeScriptSourceMap>true</TypeScriptSourceMap>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)' == 'Release'">
  <TypeScriptRemoveComments>true</TypeScriptRemoveComments>
  <TypeScriptSourceMap>false</TypeScriptSourceMap>
</PropertyGroup>

<Import
    Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)\TypeScript\Microsoft.TypeScript.targets"
    Condition="Exists('$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)\TypeScript\Microsoft.TypeScript.targets')" />
```

### ToolsVersion 

The value of `<TypeScriptToolsVersion>1.7</TypeScriptToolsVersion>`
property in the project file identifies the compiler version to use to
build (1.7 in this example). This allows a project to build against the
same versions of the compiler on different machines.

If `TypeScriptToolsVersion` is not specified, the latest compiler
version installed on the machine will be used to build.

Users using newer versions of TS, will see a prompt to upgrade their
project on first load.

### TypeScriptCompileBlocked 

If you are using a different build tool to build your project (e.g.
gulp, grunt , etc.) and VS for the development and debugging experience,
set `<TypeScriptCompileBlocked>true</TypeScriptCompileBlocked>` in your
project. This should give you all the editing support, but not the build
when you hit F5.

### TypeScriptEnableIncrementalMSBuild (TypeScript 4.2 Beta and later) 

By default, MSBuild will attempt to only run the TypeScript compiler
when the project's source files have been updated since the last
compilation. However, if this behavior is causing issues, such as when
TypeScript's
[`incremental`](https://www.typescriptlang.org/tsconfig#incremental)
option is enabled, set
`<TypeScriptEnableIncrementalMSBuild>false</TypeScriptEnableIncrementalMSBuild>`
to ensure the TypeScript compiler is invoked with every run of MSBuild.

 
© 2012-2023 Microsoft\
Licensed under the Apache License, Version 2.0.\
https://www.typescriptlang.org/docs/handbook/compiler-options-in-msbuild.html>

