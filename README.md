# Control Flow: Operators

## Learning Goals

- Use common comparison functions for control flow (`==`, `!=`, `>`, `<`)
- Use common operators for control flow (`&`, `|`, `~`, `^`)
- Understand the differences in syntax between Python and JavaScript

## Introduction

Just like JavaScript, Python has several ways we can control the flow of
execution in our programs:

- We can use conditional statements like `if/else` and `try/except`
- We can use looping constructs like `for` and `while`

Using these control flow constructs means we're taking our code out of the
normal flow of execution (top-to-bottom, one line at a time) and instead
providing some instructions to change that order. As you've surely seen in
JavaScript, conditional statements and loops are critical for writing
applications.

In the next series of lessons, we'll explore common approaches to control flow,
and learn some new syntax that is unique to Python.

## Conditional Operators

In general, using control flow in any language means running certain code **if
some condition is met**. That means that in order to use control flow
effectively, it's important to know how to use conditional operators to
compare values.

## Comparison Operators

In Python, many built-in classes have the following functions that can be used to
compare two values:

- `>`: greater than
- `>=`: greater than or equal to
- `<`: less than
- `<=`: less than or equal to
- `==`: equal to
- `!=`: not equal to

Unlike in JavaScript, the `==` function in Python **will not coerce strings to
numbers** before comparing them, or perform some of the other type coercions
that JavaScript does. For example, in JavaScript, using the `==` operator can
lead to some strange behavior:

```js
"1" == 1
// => true
0 == []
// => true
[] == ![]
// => true 🤔
```

In Python, the `==` function checks if the objects on both sides are considered the
equivalent values:

```py
"1" == 1
# False
1 == 1
# True
```

There are some differences between Python's `==` and JavaScript's `===` though. In
JavaScript, the `===` operator checks if both objects have the same identity,
i.e. refer to the same space in memory. For example, in JavaScript, this example
returns `false` because the two arrays are unique objects in memory:

```js
[1, 2, 3] === [1, 2, 3];
// => false
```

In Python, this example returns `True` because Python considers these to have
equivalent values:

```py
[1, 2, 3] == [1, 2, 3]
# True
```

Python will also check if an Integer has the equivalent value to a Float, even
though they're technically different data types:

```py
1.0 == 1
# True
```

> **Note**: While Python does have an operator, `is`, that is similar to
> JavaScript's `===`, **it is not used the same way as it is in JavaScript**.
> There are very few scenarios when you want to use the `is` operator in
> Python; in general, for comparing data, you want to use the `==`. [See here for
> examples][Python is] if you're curious about what this operator does.

[Python is]: https://stackoverflow.com/questions/21774629/python-is-vs-javascript

## Logical Operators

Python has the same logical operators you'll find in many other languages,
including JavaScript:

- `&`: Logical **and**. Are both values truthy?
- `|`: Logical **or**. Is one or the other value truthy?
- `^`: Logical **xor**. Is one (but not the other!) value truthy?
- `not`: **not**. Coerces the data to its boolean equivalent, then reverses it
  (`True` becomes `False`, and vice versa).

```py
True & True
# True
False & False
# False
False & True
# False
True | True
# True
False | False
# False
False | True
# True
True ^ True
# False
False ^ False
# False
False ^ True
# True
not True
# False
not not True
# True
```

## Ternary Operators

Python also allows us to use **ternary operators** (or _conditional
expressions_) to evaluate the truthiness of complex statements in a single
line.

```py
age = 1

is_baby = 'baby' if age < 2 else 'not a baby'
```

This is the equivalent of the following `if/else` statement:

```py
age = 1
if age < 2:
  is_baby = 'baby'
else:
  is_baby = 'not a baby'
```

## Conclusion

In the coming lessons, we'll be writing some functions that use control flow,
so make sure to keep these operators for comparing data in mind — they'll be
very important to your ability to write conditional logic and looping code
successfully!

## Resources

- [Python equality](https://realpython.com/courses/python-is-identity-vs-equality)
- [Python operators](https://www.geeksforgeeks.org/python-operators/)
- [Python ternary operators](https://book.pythontips.com/en/latest/ternary_operators.html)
