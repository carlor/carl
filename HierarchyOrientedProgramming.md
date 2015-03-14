**HOP**, or Hierarchy-Oriented-Programming, is a programming method which focuses on the modification of a Single-Parent Class Tree. It is modified simply with classes being made to extend each other. Here's an example Carl code:

```
child : parent
```

Just as in pure OOP languages everything from literals to functions are objects, in pure HOP languages everything is a class:

```
number : 33
f : Function {}
```

But note the crucial distance from OOP: in OOP, objects are instances of classes. In HOP, there are no objects, only classes. While losing the convenience of objects, pure HOP languages should be able to freely modify the Class Tree:

```
foo : parent
bar : parent
baz : foo
baz : bar
baz : parent
```

How, then, does this translate into a world of classified objects? Look an an object, e.g. a cup. In OOP, this would be something like `Cup cup = new Cup();`, where `cup` is an instance of `Cup`, i.e. it is a cup. But if we can freely modify the Class Tree, we can make a class `thecup : cup`. In other words, every individual of a class is a class of it's own. If we can do that, the class-object distinction is unnecessary -- and you have pure HOP.

# How to simulate non-HOP concepts in HOP #
## Constant literals ##
How does pure OOP do it? Constant literals are objects. In pure HOP, constant literals can be classes. For example:

```
i : 4
```

The `4` literal refers to the class 4. It could be an OOP `Number4 i = new Number4();`.

## Objects ##
With HOP alone, it doesn't work. However, Carl has a not-yet-implemented property feature, and a `spec` feature that can make the HOP simulate OOP.

