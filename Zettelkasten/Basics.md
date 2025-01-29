Tags:[[Typescript]] [[webdev]] [[Programming]]

## Static Type-Checking
Typescript has a static type-checking prevents lots of error before compilation, unlike vanilla javascript. Static types systems describe the shapes and behaviour s of what values will be when the code is running.
## Non-exception Failures
In Javascript, the instructions on how it should act in case of something nonesensical are defined by the EMCAscript specifications. Due to it being shit (a function can return undefined instead of throwing an error), Typescript has to make a call over what code should be flagged as a error in its system, even if it is valid in Javascript. 
By doing do so Typescript can catch a lot of bug that wouldn't be flagged by Javascript, for example: typos, uncalled functions, basic logic errors ecc.
## Types for Tooling
Typescript uses a typechecker
## `tsc`, the Typescript Compiler
The typescript code is compiled to normal Javascript to be executed, the compilation process checks for errors (like a normal compiler)
## Emitting with Errors
Even if there is an error, an input .ts file will be translated to a .js file. the noEmitOnError compiler options prevents the creation of a .js file if there are errors.
## Explicit Types
If a type is not specified, Typescript can infer
## Strictness
The strictness setting can be changed, for example "strict" : true in a tsconfing.js file.
### noImplicitAny
Types are not infered and the type any is used (like plain Javascipt)
### strictNullChecks
this flag mekes handling null and undefined more explicit, forcing the programmer to handle them