# Controlling flow

Sometimes you have to control your application's flow
depending on input parameters. `if` and `else` are
your friends:

    if (a == 5) {
        writeln("Condition is met");
    } else if (a > 10) {
        writeln("Another condition is met");
    } else {
        writeln("Nothing is met!");
    }

When an `if` or `else` block just contains one statement
the braces can be omitted.

D provides the same operators as C/C++ and Java for testing
variables for equality or compare them otherwise:

* `==` and `!=` for testing equality and inequality
* `<`, `<=`, `>` and `>=` for testing less (- or equal) and greater (- or equal)

For combining multiple conditions the `||` operator represents
the logical *OR*, and `&&` the logical *AND*.

D also defines a `switch`..`case` statement which lets you take
action depending on the value of *one* variable. `switch`
works with all basic types as well as strings!
It's even possible to define ranges for integral types
using the `case START: .. case END:` syntax. Make sure to
take a look at the source code example.

### In-depth

- [Expressions in detail](https://dlang.org/spec/expression.html)

## {SourceCode}

```d
import std.stdio;

void main()
{
    int c = 5;
    // This is EVIL but works
    if (c >= 0 && c < 11)
    switch(c) {
        case 0: .. case 9:
            writeln(c, " is within 0-9");
            break; // necessary!
        case 10:
            writeln("A Ten!");
            break;
        default: // if nothing else matches
            writeln("Nothing");
            break;
    }
}
```