# csyn

## Preprocessor to add coffeescript syntax features to standard javascript

Csyn is a preprocessor that allows standard javascript to be created using many syntax features stolen from coffeescript.  When combined with es6 you get a "language" that is similar to coffeescript but is real javascript with simple syntax substitutions.

Csyn is so simple that it could almost be written with all regex replacements.  For example the keyword `->` is replaced with `function`.  A more complex example is the whitespace-significant indentation being replaced by braces.

### Motivation

I have used coffeescript exclusively for four or five years and loved it.  When I originally looked at changing from coffeescript to es6 I thought I could never use it because it still uses the horrible C syntax with all the noise.  Then it occured to me that something like csyn could fix that.  You write the code mentally as real javascript but without the noise.

### Features

This is a wish-list.  Some may not be included and I assume more will be added.

- Works with babel to support most browser versions
- Significant whitespace, no more ugly pyramid of braces
- Skinny and fat arrows with almost the same semantics as coffeescript
- Removes need for `var` before destructuring
- Converts undefined to null in parameters to fix es6 problem of dropping params.
- Allows commonjs module `require` syntax
- Removes extra spaces in mult-line strings
- Allow variables in class prototypes
- Wrap entire module with protective function
- In many ways csyn is the best of both CS and JS

### Atom integration out of the gate

Not only will a standard csyn grammar support highlighting, but converting the buffer between csyn and js will be supported with one command.

Also, there will be a mode where the file is always stored as javascript but edited as csyn.  This eliminates the need to run the pre-processor at build time.  This will also allow editing other's javascript files in csyn without them even knowing about csyn.

### Status

Just a specification at this point.  There is nothing more than this readme.  However, this looks like a simple project to implement.  I doubt that an AST will be needed.  Most will be done with regexes.

### Why switch from Coffeescript

Many coffeescript users like me are convering to es6.  For a quick writeup comparing the two see [this](https://gist.github.com/danielgtaylor/0b60c2ed1f069f118562)

Here is my personal list of reasons for changing to es6.

- **Improved debugging:** Even with source maps coffeescript is harder to debug.  
  - You can't hover over a variable like `@var` to see the value
  - You can't evaluate coffeescript in the console  
  - Stepping can be confusing because of line mismatch.  I sometimes have to step many times to get past one line of coffeescript.
- **Larger community:**  Coffeescript has divided the community.  I can finally publish code without people bitching they can't read it.
- **Advanced features:**  While some coffeescript features are lost, like all code being expressions, there are many, if not more, features gained from es6, like iterators.

### License
  Csyn is copyright Mark Hahn via the MIT license.
