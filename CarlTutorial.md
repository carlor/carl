# Hello, World! #
As always, we must start by outputting the string `"hello world"` to standard output. In Carl, this is easily accomplished:

```
PrintLn "hello world"
```

Classes of the standard library are written starting with the upper case. It is recommended that your classes start with a lower case.

# Basic Literals, Classes #
To use a class, it only has to be mentioned as descending from something else, and Carl will know it's a class. To link a child to it's parent, the `:` operator is used. `|` is the "sibling" operator - it becomes the child of the parent.

```
parent : U # U is the Universal Class.
bro : parent
sis | bro
# now bro and sis are children of "parent"
```

What's the use of the sibling operator? Check this out:

```
x : 4
y : x
x : 5
PrintLn y
```

One would expect this to print `4`. Actually, this would produce undefined behavior. This is because `y` is a grandchild of `4`, not a child. When commanding `y : x`, you make `y` a child of `x` a child of `4`. You want to make it a sibling.

Use the sibling operator when dealing with values, unless you know it should be the child operator.

Other literals include floating points `3.2`, characters `'\n'`, strings (`"hey, dude!\n"`), booleans (`True && False`), and functions (next topic).

# Functions #
Functions types are declared of the format `Function [param]... { body `}.

Functions, of course, take classes as arguments and return a class (`U` by default).

The classic factorial:

```
factorial : Function n {
     if (!n < 0) return U
     if (!n < 2) return 1
     return recur (!n - 1)
}
```

A few things to notice: the `!` operator and the `recur` keyword. The former is a symbol which means the parent of, and the latter refers to recursively calling the function.

How do we make sure `n` is an integer? We'll get to that later.